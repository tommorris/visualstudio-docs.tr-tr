---
title: VSIX paketi anatomisi | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- visual studio extension
- vsix
- packages
ms.assetid: 8b86d62f-c274-4e91-82e0-38cdb9a423d5
caps.latest.revision: "15"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 519993c8527b0cd64c283416cd60eb48112e6886
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="anatomy-of-a-vsix-package"></a>VSIX paketi anatomisi
VSIX paketi bir veya daha fazla Visual Studio uzantıları, sınıflandırmak ve Uzantıları'nı yüklemek için Visual Studio kullanan meta verileri ile birlikte içeren bir .vsix dosyasıdır. Bu meta veri VSIX bildirimini ve [Content_Types] .xml dosyasında yer alır. VSIX paketi yerelleştirilmiş Kurulum metin sağlamak için bir veya daha fazla Extension.vsixlangpack dosyalar da içerebilir ve bağımlılıklarını yüklemek için ek VSIX paket içerebilir.  
  
 VSIX paketi açık paketleme kuralları (OPC) standart biçimdedir. Paket ikili dosyalarını içerir ve destekleyen dosyaları, [Content_Types] .xml dosyası ve bir .vsix ile birlikte bildirim dosyası. Bir VSIX paketi birden çok proje veya kendi bildirimleri sahip bile birden çok paket çıktısını içerebilir.  
  
> [!NOTE]
>  VSIX paketlerinde dosyaların adlarını boşluk içermemelidir ya da devre dışı olarak Tekdüzen Kaynak Tanımlayıcıları (URI) içinde ayrılmış karakterler tanımlanan altında [ \[RFC2396\]](http://go.microsoft.com/fwlink/?LinkId=90339).  
  
## <a name="the-vsix-manifest"></a>VSIX bildirimi  
 VSIX bildirimini uzantısı yüklü olmasını ve aşağıdaki VSX şeması hakkında bilgi içerir. Daha fazla bilgi için bkz: [VSIX uzantı şema 1.0 başvurusu](http://msdn.microsoft.com/en-us/76e410ec-b1fb-4652-ac98-4a4c52e09a2b). Bir örnek VSIX listesi için bkz: [PackageManifest öğesi (kök öğesi, VSX şema)](http://msdn.microsoft.com/en-us/f8ae42ba-775a-4d2b-976a-f556e147f187).  
  
 VSIX bildirimini adlandırılmalıdır `extension.vsixmanifest` zaman onu dahil .vsix dosyasında.  
  
## <a name="the-content"></a>İçerik  
 VSIX paketi şablonları, araç kutusu öğelerini, VSPackages veya başka bir Visual Studio tarafından desteklenen uzantı türü içerebilir.  
  
## <a name="language-packs"></a>Dil Paketleri  
 VSIX paketi bir kez veya yükleme sırasında yerelleştirilmiş metin sağlamak için daha fazla Extension.vsixlangpack dosyaları içerebilir. Daha fazla bilgi için bkz: [yerelleştirme VSIX paket](../extensibility/localizing-vsix-packages.md).  
  
## <a name="dependencies-and-references"></a>Bağımlılıklar ve başvurular  
 VSIX paketi diğer VSIX paketleri başvuru olarak içerebilir. Her bu diğer paketleri kendi VSIX bildirimini eklemeniz gerekir.  
  
 Bir kullanıcı bağımlılıklara sahip bir uzantı yüklemeniz çalışırsa, yükleyici gerekli derlemeleri kullanıcı sistemde yüklü olduğunu doğrular. Gerekli derlemeleri bulunmazsa, **Uzantılar ve güncelleştirmeler** eksik bir derleme listesi görüntüler.  
  
 Bir veya daha fazla uzantı bildirimi içeriyorsa, [başvuru](http://msdn.microsoft.com/en-us/32c52934-e81e-4b53-8cb6-4df45ef7bfa8) öğeleri **Uzantılar ve güncelleştirmeler** sistemde yüklü uzantıları her başvuru bildirimi karşılaştırır ve yükler zaten yüklü değilse başvurulan uzantısı. Başvurulan uzantısı'nın önceki bir sürümünü yüklediyseniz, daha yeni sürümü değiştirir.  
  
 Birden çok proje çözümdeki bir proje ile aynı çözüm içinde başka bir projeye bir başvuru içeriyorsa, VSIX paketi, proje bağımlılıklarını içerir. Dahili Proje ve ardından, başvuru tıklayarak bu davranışı geçersiz kılabilirsiniz **özellikleri** ayarı penceresinde **VSIX çıktı grupları dahil** özelliğine `BuiltProjectOutputGroup`.  
  
 Uydu DLL'leri başvurulan derlemelerden VSIX pakete eklemek için Ekle `SatelliteDllsProjectOutputGroup` için **VSIX çıktı grupları dahil** özelliği.  
  
## <a name="installation-location"></a>Yükleme Konumu  
 Yükleme sırasında **Uzantılar ve güncelleştirmeler** % LocalAppData%\Microsoft\VisualStudio\14.0\Extensions altında bir klasör içinde VSIX paket içeriğini arar.  
  
 Kullanıcıya özgü dizin LocalAppData % olduğu için varsayılan olarak, yalnızca geçerli kullanıcı için yükleme uygular. Ancak, ayarlarsanız [AllUsers](http://msdn.microsoft.com/en-us/ac817f50-3276-4ddb-b467-8bbb1432455b) bildirime öğesinin `True`, uzantı altında yüklü... \\ *VisualStudioInstallationFolder*\Common7\IDE\Extensions ve bilgisayarın tüm kullanıcıları için kullanılabilir duruma gelir.  
  
## <a name="contenttypesxml"></a>[Content_Types] .xml  
 Genişletilmiş .vsix dosyasında dosya türleri [Content_Types] .xml dosyası tanımlar. Visual Studio paketin yüklenmesi sırasında bu dosyayı kullanır ancak dosya yüklemez. Bu dosya hakkında daha fazla bilgi için bkz: [[Content_types] .xml dosya yapısı](the-structure-of-the-content-types-dot-xml-file.md).  
  
 Açık paketleme kuralları (OPC tarafından) standart [Content_Types] .xml dosyası gerekir. OPC hakkında daha fazla bilgi için bkz: [OPC: A yeni standart için paketleme verilerinizi](http://go.microsoft.com/fwlink/?LinkID=148207) MSDN Web sitesinde.