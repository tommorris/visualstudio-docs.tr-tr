---
title: Gözat ve bir .NET türünü seç iletişim kutusu | Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- TypeBrowser.UI
- ActivityTypeResolver.UI
ms.assetid: 864b60b6-a070-4e5c-aa5b-a25341b57ea6
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- dotnet
ms.openlocfilehash: 04aba24d3dffc96fb8e5288d74322258fa77ce19
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="browse-and-select-a-net-type-dialog-box"></a>Gözat ve bir .NET türünü seç iletişim kutusu

İçinde **özellikleri** pencere, iletişim kutularını veya tasarımcıları seçtiğinizde değişken Tasarımcısı gibi **türleri için Gözat...**  veri türleri listesinden olan **göz atın ve .NET türü seçin** iletişim kutusu (kısaltılmış biçimde "türü tarayıcı" olarak adlandırılır). Bu iletişim kutusunda derlemeleri ve projeleri bir ağaç görünümünden bir türü seçebilirsiniz.

 Bu iletişim kutusu, kullanıcı senaryoları, aşağıdakiler de dahil olmak üzere çeşitli kullanılmaz:

-   Bir değişken veya değişken türünü ayarlarken.

-   Genel etkinlik için bir türü seçerken.

-   Bir catch üzerinde eklerken <xref:System.Activities.Statements.TryCatch> etkinlik.

> [!NOTE]
> Tür tarayıcı olmayan çok boyutlu dizi türleri ancak Visual Basic Basit dizi türleri görüntüleyebilirsiniz. Bkz: [basit diziler](http://go.microsoft.com/fwlink/?LinkId=195226) ve [çok boyutlu diziler](http://go.microsoft.com/fwlink/?LinkId=195227) Ayrıntılar için.

## <a name="selecting-a-value-or-reference-type-from-the-type-browser"></a>Bir değer veya başvuru türündeki türü tarayıcıdan seçme

#### <a name="to-select-a-value-or-reference-type-from-the-type-browser"></a>Bir değer veya başvuru türünde türü tarayıcıdan seçmek için

1.  İçinde **türü adı** kutusunda, kullanmak istediğiniz türünün adını girin.

2.  Aşağıdakilerden birini yapın:

    -   Kullanmak istediğiniz türünün adını ağaçta göründüğünde **türü adı** kutusunda, türü seçmek için çift tıklayın.

    -   Yeterli sayıda karakter **türü adı** kutusunu kullanmak istiyorsanız ve ENTER tuşuna basın türü seçmek için tür benzersiz şekilde tanımlamak için

#### <a name="to-select-a-generic-type-from-the-type-browser"></a>Genel bir tür türü tarayıcıdan seçmek için

1.  İçinde **türü adı** kutusunda, kullanmak istediğiniz türü adını yazın.

2.  Kullanmak istediğiniz türünün adını ağaçta göründüğünde **türü adı** kutusunda, aşağı açılan kutuları neden seçmek için türü görünür tıklatın.

     Aşağı açılan kutuları genel kapatın ve ardından kullanmak istediğiniz türü seçin **Tamam**.

## <a name="types-displayed-in-the-type-browser"></a>Türü tarayıcıda görüntülenen türleri
 Türü tarayıcıda görüntülenen türleri türü tarayıcı nasıl başlatıldı bağlı olarak değişebilir. Tür tarayıcı içinde bir iş akışı projeden başlatıldı, **vs2010**tarafından başvurulan derlemeleri türlerinde tümünün varsayılan ve başvurulan projeleri gösterilir. Tür tarayıcı dışında gelen başlatıldı, bir **vs2010** proje sistem (gibi rehosted iş akışı uygulaması olduğu gibi veya tek başına iş akışı dosyası), sonra da varsayılan olarak tüm AppDomain'e derlemeler türlerinden gösterilir .

 Etkinlik Tasarımcısı geliştiriciler tarafından türü tarayıcı türlerinde filtrelenebilir. Verilen herhangi bir etkinlik için yalnızca bir alt kümesini türleri görebilirsiniz. Örneğin, <xref:System.Activities.Statements.TryCatch> yalnızca türleri etkinlik, türetilen <xref:System.Exception> türü tarayıcıda gösterilir.

## <a name="filtering-search-results-in-the-type-browser"></a>Türü tarayıcıda arama sonuçlarını filtreleme
 Türlerinde listesi **türü adı** kutusunu bir eşleşme bulmak için daha fazla karakter yazarken kısa alır. Yalnızca tam adı yazdığınız dize ile başlayan türleri veya kısa adı yazdığınız dize ile başlayan türleri filtrelenmiş listede görüntülenir.

 Örneğin:

1.  Yazmaya **işlemi** eşleşen <xref:System.OperationCanceledException> ama <xref:System.InvalidOperationException>. Eşleştirilecek <xref:System.InvalidOperationException>, System.I veya geçersiz yazmaya başlayın.

2.  Yazmaya **genel** eşleşen <xref:System.GenericUriParser> ancak türlerini değil <xref:System.Collections.Generic> ad alanı. Türlerinde aramak için <xref:System.Collections.Generic> ad alanı, ad alanının türü tam adı.

## <a name="selecting-a-service-contract-using-the-type-browser-dialog"></a>Tür Tarayıcı iletişim kutusu kullanılarak bir hizmet sözleşmesini seçme
 Bir hizmet sözleşmesi türü seçerken, türü tarayıcı türleri yalnızca gösterir. <xref:System.ServiceModel.ServiceContractAttribute> özniteliği.

## <a name="see-also"></a>Ayrıca bkz.

- [Etkinlik Tasarımcılarını kullanma](../workflow-designer/using-the-activity-designers.md)