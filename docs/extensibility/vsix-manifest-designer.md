---
title: VSIX bildirim Tasarımcısı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- VS.Sdk.VsixManifestEditor
helpviewer_keywords:
- vsixmanifest
- vsix manifest
- manifest designer
ms.assetid: 5a691e77-cf91-430d-90ea-361d9031ef83
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 5b90f8acd95d913e563ff167e21b743cbffec2ac
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="vsix-manifest-designer"></a>VSIX bildirim Tasarımcısı
Visual Studio uzantısı yükleme davranışını ayarlayan bir VSIX paket bildirim dosyası, değiştirir.  
  
 **VSIX bildirim Tasarımcısı** temel VSIX şeması eşler. Şemadaki her öğenin Tasarımcısı'nda karşılık gelen bir denetim kullanılarak ayarlanabilir. Şeması hakkında daha fazla bilgi için bkz: [VSIX uzantı şema 2.0 başvurusu](../extensibility/vsix-extension-schema-2-0-reference.md).  
  
 Açmak için **VSIX bildirim Tasarımcısı**, source.extension.vsixmanifest dosyasında bulun **Çözüm Gezgini**ve dosyayı açın. Dosya geçerli XML içermiyorsa, bildirim tasarımcısını açılmaz.  
  
> [!NOTE]
>  Paket yapılandırıldığında Source.extension.vsixmanifest extension.vsixmanifest çıkışı yapılır.  
  
## <a name="uielement-list"></a>UIElement Listesi  
 **VSIX bildirim Tasarımcısı** şemanın en üst düzey bu öğelere karşılık gelen dört bölüm içerir:  
  
-   Meta Veriler  
  
-   Hedefleri yükleyin  
  
-   Varlıklar  
  
-   Bağımlılıklar  
  
 Başlık alanı aşağıdaki denetimleri içerir.  
  
 **Ürün adı**  
 Uzantı adı açıklar.  
  
 **Ürün Kimliği**  
 Bu paket için benzersiz kimlik bilgilerini belirtir.  
  
 **Yazar**  
 Uzantı yazarına adını belirtir.  
  
 **Sürüm**  
 Uzantısı sürüm numarasını belirtir.  
  
 **Meta veri** sekmesi aşağıdaki denetimleri içerir.  
  
 **Açıklama**  
 Görüntülenecek uzantısı, metin açıklaması sağlanıyor **Uzantı Yöneticisi**.  
  
 **Dil**  
 Bildiriminde metinsel verilere karşılık gelen paket için varsayılan dili belirtir. `Language` Özniteliği aşağıdaki ortak dil çalışma zamanı (CLR) yerel ayar kodu kuralı için kaynak grupları, örneğin, en-us, tr, fr-fr. Varsayılan olarak, nötr değerdir; Bu paketin tüm Visual Studio dil sürümünü çalışacağını anlamına gelir.  
  
 **Lisans**  
 Var olan kullanıcı lisansı içeren metin dosyasını belirtir.  
  
 **Simgesi**  
 Görüntülenecek simgesini içeren grafik dosyası (.png, .bmp, .jpeg, .ico) belirtir **Uzantı Yöneticisi**, bir simge varsa. Simge görüntüsü 32 x 32 piksel olmalıdır veya bu boyutlara yeniden boyutlandırılır. Hiçbir simge belirtilirse, **Uzantı Yöneticisi** varsayılan bir simge kullanır.  
  
 **Önizleme görünümü**  
 Görüntülenecek önizleme görüntüsünü içeren grafik dosyası (.png, .bmp, .jpeg, .ico) belirtir **Uzantı Yöneticisi**, Önizleme görünümü mevcut değilse. Önizleme görünümü 200 x 200 piksel olması gerekir. Önizleme görüntüsü belirtilirse, **Uzantı Yöneticisi** varsayılan görüntü kullanır.  
  
 **Etiketleri**  
 Arama ipuçları için kullanılacak metni etiketleri ekler.  
  
 **Sürüm Notları**  
 Sürüm notları içeren dosyası (.txt, .rtf) belirtir. Ayrıca sürüm notları görüntüler bir Web sitesinin URL'sini alır.  
  
 **Başlarken Kılavuzu**  
 Uzantı veya içeriği VSIX paketi nasıl kullanılacağı hakkında bilgi içeren bir dosyası (.txt, .rtf) belirtir. Uzantısı yükleme tamamlandığında, bu kılavuzda görüntülenir. Ayrıca Kılavuzu görüntüleyen bir Web sitesinin URL'sini alır.  
  
 **Daha fazla bilgi URL'si**  
 Ürün hakkında ek bilgi içeren bir Web sitesinin URL'sini belirtir.  
  
 **Yükleme hedefleri** sekmesi aşağıdaki denetimleri içerir.  
  
 **Yükleme türü**  
 Listeler **Visual Studio Uzantısı** ve **uzantısı SDK** yükleme türleri hedefleyin. Seçenekler, seçtiğiniz türüne bağlı olarak değişir.  
  
 **Visual Studio uzantısı**  
 Listeler **InstallationTarget** nasıl paket yüklenebilir ve bu uzantı hangi Visual Studio ürünlerle yüklenebilir açıklayan öğeler. Her ürün adı ve sürümü veya sürüm aralığına göre ayrı olarak tanımlanır.  Ürünler, değiştirilebilir ve Silinen listesine eklenir. Ad ve bir ürünün sürümü karşılık **kimliği** ve **sürüm** ilişkili özniteliklerini **InstallationTarget** öğesi.  
  
 **Sürüm aralığı** olduğundan [12,0, 14,0] ve aşağıdaki gösterim kullanır:  
  
-   [-dahil en düşük sürüm  
  
-   ]-dahil en yüksek sürüm  
  
-   (-özel en düşük sürüm  
  
-   )-özel en yüksek sürüm  
  
-   Tek sürüm # - yalnızca belirtilen sürüm  
  
 **Uzantı SDK**  
 Belirli bir ürün ve sürüm için kapsamlı olmayan genel bir yükleme belirtir. **Hedef Platform tanımlayıcısı** , "hedeflediği Windows," gibi bir platformdur. **Hedef Platform sürümü** 8.0, hedef platformunuzu gibi sürümü. **SDK adı** ve **SDK sürümü** adını ve SDK'sı sürüm numarasını sırasıyla şunlardır.  
  
 **Bu VSIX tüm kullanıcılar için yüklenir (yükseltme yükleyin gerektirir)** onay kutusu  
 Bu onay kutusu seçili değilse bu uzantı tüm kullanıcılar için yüklenir; Aksi takdirde, yalnızca geçerli kullanıcı için yüklenir.  
  
 **Bu VSIX Windows Installer tarafından yüklendi** onay kutusu  
 Bu onay kutusunu seçtiyseniz bu uzantısı Windows Installer (.msi dosyası); tarafından yüklenir Aksi takdirde tipik VSIX paket (.vsix dosyası) olarak yüklenir.  
  
 **Varlıklar** sekmesi aşağıdaki denetimleri içerir.  
  
 **Varlıkların listesi**  
 Uzantı veya içerik öğeleri açıklanır varlık öğeleri listeler bu paketini yüzeyleri. Ayrı ayrı her bir uzantı veya içerik öğesi kaynağı, türü ve yol tarafından listelenir. Uzantıları ve içerik öğeleri, değiştirilebilir ve Silinen listesine eklenir. Türü ve yol, bir uzantı veya içeriği öğenin karşılık gelen `Type` ve `Path` ilişkili özniteliklerini `Asset` öğesi. Aşağıdaki türlerden bilinmektedir:  
  
-   Microsoft.VisualStudio.Package  
  
-   Microsoft.VisualStudio.MefComponent  
  
-   Microsoft.VisualStudio.ToolboxControl  
  
-   Microsoft.VisualStudio.Samples  
  
-   Microsoft.VisualStudio.ProjectTemplate  
  
-   Microsoft.VisualStudio.ItemTemplate  
  
-   Microsoft.VisualStudio.Assembly  
  
-   Microsoft.ExtensionSDK  
  
 Eklemek veya bir varlığı düzenlemek için varlık dosya sistemi ve projesinin adı geçerli çözümdeki bir proje veya bir dosya olup olmadığını varlık türünü belirtmeniz gerekir. Ayrıca, katıştırılmış kaydedileceği klasörün adını belirtebilirsiniz.  
  
 Ayrıca, kendi türlerinizi oluşturabilir ve bunları benzersiz adlar verin.  
  
 **Bağımlılıkları** sekmesi aşağıdaki denetimleri içerir.  
  
 **Adı, kaynak ve sürüm aralığı**  
 Bu paket bağımlı diğer paketleri bu paket, bağımlılık öğeleri listeler. Bir bağımlılık paketi belirtilirse, bu paket yüklenmeden önce yüklenmelidir; Aksi takdirde, bu paket yüklemeniz gerekir.  
  
 Bağımlılık paket tanımlayıcısı, ad, sürüm aralığı, kaynak ve nasıl bağımlılık çözümlenmesi olduğundan tarafından belirtilir. Her bir bağımlılık paket adı, sürüm ve kaynak tarafından ayrı olarak listelenir. Bağımlılık paketler, değiştirilebilir ve Silinen listesine eklenir.  
  
 Tanımlayıcı eşleşmelidir `ID` bağımlılık paket meta verileri özniteliği. Kaynak geçerli çözüm, şu anda yüklü bir uzantısı ya da bir dosyaya projede olabilir. **Nasıl çözülen bağımlılığın mu** ayarı göreli yolun iç içe geçmiş bir paketin veya bağımlılık indirme konumu URL'sini olabilir. Kimliği, sürüm ve bağımlılık paketi çözümleme karşılık `Id`, `Version`, ve `Location` ilişkili özniteliklerini `Dependency` öğesi.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [VSIX uzantısı 2.0 şema başvurusu](../extensibility/vsix-extension-schema-2-0-reference.md)   
 [Bir VSIX Paketinin Anatomisi](../extensibility/anatomy-of-a-vsix-package.md)