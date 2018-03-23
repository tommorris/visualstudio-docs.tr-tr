---
title: 'Nasıl yapılır: yerleşik yazı tipleri ve renk düzenini erişim | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- fonts, accessing built-in
- font and color control [Visual Studio SDK], categories
- colors, accessing built-in schemes
ms.assetid: 6905845e-e88e-4805-adcf-21da39108ec7
caps.latest.revision: ''
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload:
- vssdk
ms.openlocfilehash: 1f329464b37d9b7de037523735cc09ff95dce3bd
ms.sourcegitcommit: 67374acb6d24019a434d96bf705efdab99d335ee
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/22/2018
---
# <a name="how-to-access-the-built-in-fonts-and-color-scheme"></a>Nasıl yapılır: yerleşik yazı tipleri ve renk düzenini erişim
Visual Studio tümleşik geliştirme ortamı (IDE) Düzenleyicisi penceresini ile ilişkili bir düzeni yazı tiplerini ve renkleri vardır. Bu düzen üzerinden erişebilirsiniz <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextView> arabirimi.

 Yerleşik yazı tiplerini ve renkleri düzenini kullanmak için bir VSPackage gerekir:

-   Varsayılan yazı tiplerini ve renkleri hizmetle birlikte kullanmak üzere bir kategori tanımlayın.

-   Kategori varsayılan yazı tiplerini ve renkleri sunucusuna kaydedin.

-   Belirli bir pencere öğeleri yerleşik görüntüleme ve kategorileri kullanarak kullandığını IDE bildirmek <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextEditorPropertyCategoryContainer> ve <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextEditorPropertyContainer> arabirimleri.

 IDE penceresi için bir tanıtıcı olarak elde edilen kategoriyi kullanır. Kategori adı görüntülenir **ayarlarını göster:** açılan kutusunda **yazı tiplerini ve renkleri** özellik sayfası.

### <a name="to-define-a-category-using-built-in-fonts-and-colors"></a>Yerleşik yazı tipleri ve renkler kullanarak bir kategori tanımlamak için

1.  Rastgele bir GUID oluşturun.

     Bir kategori benzersiz şekilde tanımlamak için kullanılan bu GUID**.** Bu kategori IDE'nin varsayılan yazı tipleri ve renkler belirtimi yeniden kullanır.

    > [!NOTE]
    >  Yazı tipi ve renk verilerle alınırken <xref:Microsoft.VisualStudio.Shell.Interop.IVsFontAndColorEvents> veya diğer arabirimleri VSPackages yerleşik bilgilere referans bu GUID kullanın.

2.  IDE içinde görüntülendiğinde gerektiğinde yerelleştirilebilir böylece kategori adı bir dize tabloya VSPackage'nın kaynakları (.rc) dosyası içinde eklenmesi gerekir.

     Daha fazla bilgi için bkz: [ekleyerek veya silerek bir dize](/cpp/windows/adding-or-deleting-a-string).

### <a name="to-register-a-category-using-built-in-fonts-and-colors"></a>Yerleşik yazı tipleri ve renkler kullanarak bir kategori kaydetmek için

1.  Özel türde bir kategori aşağıdaki konumda kayıt defteri girişi oluşturun:

     [HKLM\SOFTWARE\Microsoft \Visual Studio\\*\<Visual Studio version>*\FontAndColors\\*\<Category>*]

     *\<Kategori >* kategorisi yerelleştirilmemiş adıdır.

2.  Stok yazı tipleri ve renk şeması ile dört değerleri kullanmak için kayıt defteri doldurun:

    |Ad|Tür|Veri|Açıklama|
    |----------|----------|----------|-----------------|
    |Kategori|REG_SZ|GUID|Stok yazı tipi ve renk düzenini içeren bir kategori tanımlayan rasgele bir GUID.|
    |Paket|REG_SZ|GUID|{F5E7E71D-1401-11D1-883B-0000F87579D2}<br /><br /> Bu GUID varsayılan yazı tipi ve renk yapılandırmaları kullanan tüm VSPackages tarafından kullanılır.|
    |NameID|REG_DWORD|Kimlik|Yerelleştirilebilir kategori adı VSPackage içinde kaynak kimliği.|
    |ToolWindowPackage|REG_SZ|GUID|Uygulama VSPackage GUID <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextView> arabirimi.|

### <a name="to-initiate-the-use-of-system-provided-fonts-and-colors"></a>Sistem tarafından sağlanan yazı tiplerini ve renkleri kullanımını başlatmak için

1.  Bir örneğini oluşturmak <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextEditorPropertyCategoryContainer> arabirimi pencerenin uygulama ve başlatma bir parçası olarak.

2.  Çağrı <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextEditorPropertyCategoryContainer.GetPropertyCategory%2A> bir örneği elde etmek için yöntemi <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextEditorPropertyContainer> geçerli karşılık gelen arabirimi <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextView> örneği.

3.  Çağrı <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextEditorPropertyContainer.SetProperty%2A> iki kez.

    -   Bir kez çağıran `VSEDITPROPID_ViewGeneral_ColorCategory`bağımsız değişken olarak.

    -   Bir kez çağıran `VSEDITPROPID_ViewGeneral_FontCategory` bağımsız değişken olarak.

     Bu ayarlar ve varsayılan yazı tiplerini ve renkleri Hizmetleri penceresinin bir özellik olarak kullanıma sunar.

## <a name="example"></a>Örnek
 Aşağıdaki örnek, yerleşik yazı tiplerini ve renkleri kullanımını başlatır.

```cpp
CComVariant vt;
CComQIPtr<IVsTextEditorPropertyCategoryContainer> spPropCatContainer(m_spView);
if (spPropCatContainer != NULL){
    CComPtr<IVsTextEditorPropertyContainer> spPropContainer;
    if (SUCCEEDED(spPropCatContainer->GetPropertyCategory(GUID_EditPropCategory_View_MasterSettings,
                                                          &spPropContainer))){
        CComVariant vt;CComVariant VariantGUID(bstrGuidText);
        spPropContainer->SetProperty(VSEDITPROPID_ViewGeneral_FontCategory, VariantGUID);
        spPropContainer->SetProperty(VSEDITPROPID_ViewGeneral_ColorCategory, VariantGUID);
    }
}
```

## <a name="see-also"></a>Ayrıca Bkz.

- [Yazı tipleri ve renkler kullanarak](../extensibility/using-fonts-and-colors.md)
- [Yazı tipi ve metin renklendirme için renk bilgilerini alma](../extensibility/getting-font-and-color-information-for-text-colorization.md)
- [Saklı yazı tipi ve renk ayarlarını erişme](../extensibility/accessing-stored-font-and-color-settings.md)
- [Yazı tipi ve renk genel bakış](../extensibility/font-and-color-overview.md)