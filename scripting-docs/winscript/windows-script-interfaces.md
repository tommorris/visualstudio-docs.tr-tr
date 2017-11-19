---
title: "Windows komut dosyası arabirimleri | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 4c750627-6797-4857-9f5e-e5f54371f83c
caps.latest.revision: "10"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 200a1ac1bf273e2515e1e17b6f83c2020ff9884d
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
---
# <a name="windows-script-interfaces"></a>Windows Komut Dosyası Arabirimleri
Microsoft Windows komut dosyası arabirimleri, bir komut dosyası eklemek için uygulama ve OLE Otomasyon için bir yol sağlar. Windows komut kullanan ana komut dosyası altyapılarının birden çok kaynakları ve satıcılar bileşenler arasında scripting yönetmek için kullanabilirsiniz. Komut dosyasının kendisini uyarlamasını — dil, sözdizimi, kalıcı biçimi, yürütme modeli ve benzeri — betik satıcıya bırakılır.  
  
 Windows komut dosyası belgeleri aşağıdaki bölümlere ayrılır:  
  
 [Windows komut dosyası konakları](../winscript/windows-script-hosts.md)  
  
 [Windows komut dosyası motorları](../winscript/windows-script-engines.md)  
  
 [Etkin komut dosyası hata ayıklamaya genel bakış](../winscript/active-script-debugging-overview.md)  
  
 [Etkin komut dosyası profil oluşturmaya genel bakış](../winscript/active-script-profiling-overview.md)  
  
 [Windows komut dosyası arabirimleri başvurusu](../winscript/reference/windows-script-interfaces-reference.md)  
  
## <a name="windows-script-background"></a>Windows komut dosyası arka planı  
 Windows komut dosyası arabirimleri iki kategoriye ayrılır: Windows komut dosyası ana bilgisayarları ve Windows komut dosyası motorları. Bir ana bilgisayara bir komut dosyası motoru oluşturur ve komut dosyalarını çalıştırmak için altyapı çağırır. Windows komut dosyası konakları örnekleri şunlardır:  
  
-   Microsoft Internet Explorer  
  
-   Internet yazma araçları  
  
-   Kabuk  
  
 Windows komut dosyası motoru herhangi bir dil veya çalışma zamanı ortamı için geliştirilebilir dahil olmak üzere:  
  
-   Microsoft Visual Basic Scripting Edition (VBScript)  
  
-   Perl  
  
-   Lisp  
  
 Ana bilgisayar uygulaması kadar esnek hale getirmek için Windows komut dosyası için bir OLE Otomasyon sarmalayıcı sağlanır. Ancak, komut dosyası altyapısı örneği için bu sarmalayıcı nesnesini kullanan bir ana bilgisayar denetime sahip çalışma zamanı ad alanı, Kalıcılık modeli ve Windows komut dosyası doğrudan kullandıysanız, düğmelerden benzeri yok.  
  
 Windows komut dosyası Tasarım nonauthoring konakları (örneğin, tarayıcılar ve Görüntüleyiciler) ve komut dosyası motorları (örneğin, VBScript) basit tutulabilir böylece yalnızca geliştirme ortamında gerekli arabirim öğeleri yalıtır.  
  
## <a name="windows-script-basic-architecture"></a>Windows komut dosyası temel mimarisi  
 Aşağıda Windows Script host ve bir Windows komut dosyası motoru arasındaki etkileşimler gösterilmektedir.  
  
 Ana bilgisayar ve altyapısı arasında etkileşim adımlar aşağıdaki listede verilir.  
  
1.  Bir proje oluşturun. Konak bir proje veya belge yükler. (Bu adım Windows komut dosyası için belirli değildir, ancak bütünlük açısından buraya dahil edilir.)  
  
2.  Windows komut dosyası altyapısı oluşturun. Ana bilgisayar çağrıları `CoCreateInstance` yeni bir Windows komut dosyası motoru oluşturmak için kullanılacak belirli komut dosyası altyapısı sınıf tanımlayıcısı (CLSID) belirtme. Örneğin, Internet Explorer'ın HTML tarayıcı komut dosyası altyapısı sınıf tanımlayıcısı CLSID aracılığıyla alır HTML öznitelik = \<NESNESİ > etiketi.  
  
3.  Komut dosyası yükleyin. Komut dosyası içeriğini kalıcı, ana bilgisayar komut dosyası altyapısı çağırır `IPersist*::Load` betik depolama, akış veya özellik paketi akışına yöntemi. Aksi takdirde, ana bilgisayar ya da kullanır `IPersist*::InitNew` veya [IActiveScriptParse::InitNew](../winscript/reference/iactivescriptparse-initnew.md) null bir komut dosyası oluşturmak için yöntemi. Bir komut dosyası metin kullanabilirsiniz gibi tutan bir konak [IActiveScriptParse::ParseScriptText](../winscript/reference/iactivescriptparse-parsescripttext.md) komut dosyası altyapısı komut metnini çağrıldıktan sonra akışına `IActiveScriptParse::InitNew`.  
  
4.  Adlandırılmış öğe ekleyin. Komut dosyası altyapısı ad alanına alınan her en üst düzey adlandırılmış öğesi için (örneğin, sayfalar ve formlar), konak çağırır [IActiveScript::AddNamedItem](../winscript/reference/iactivescript-addnameditem.md) yöntemi altyapının ad alanı bir giriş oluşturun. Bu adım en üst düzey adlandırılmış öğe zaten 3. adımda yüklenen betik kalıcı durumunu parçası ise gerekli değildir. Bir konak kullanmayan `IActiveScript::AddNamedItem` yerine, altyapı dolaylı olarak alt düzey öğeleri üst düzey öğelerden ana bilgisayarın kullanarak alır; alt düzey eklemek için öğeleri (örneğin, bir HTML sayfasında denetimleri) adlı `ITypeInfo` ve `IDispatch` arabirimleri.  
  
5.  Komut dosyasını çalıştırın. Konak SCRIPTSTATE_CONNECTED bayrağını ayarlayarak betik başlamasını altyapısı neden olur [IActiveScript::SetScriptState](../winscript/reference/iactivescript-setscriptstate.md) yöntemi. Bu çağrı, büyük olasılıkla statik bağlama, olayları (aşağıya bakın) takma ve bir komut dosyası için benzer bir şekilde yürütme kodu da dahil olmak üzere tüm komut dosyası altyapısı oluşturma iş gerçekleştireceği `main()` işlevi.  
  
6.  Öğe bilgileri alın. Betik altyapısı gereken üst düzey bir öğesiyle bir simge ilişkilendirmek için her zaman çağırır [IActiveScriptSite::GetItemInfo](../winscript/reference/iactivescriptsite-getiteminfo.md) verilen öğe hakkında bilgi verir yöntemi.  
  
7.  Olayları bağlayın. Gerçek komut başlamadan önce komut dosyası altyapısı tüm ilgili nesneleri olayları bağlandığı `IConnectionPoint` arabirimi.  
  
8.  Özellikleri ve yöntemleri çağırır. Komut dosyasını çalıştırır gibi komut dosyası altyapısı adlandırılmış nesneler üzerinde yöntemleri ve özellikleri başvurular gerçekleştirir `IDispatch::Invoke` veya diğer OLE bağlama mekanizmalarını.  
  
## <a name="windows-script-terms"></a>Windows komut dosyası koşulları  
 Bu liste, bu belgede kullanılan komut dosyası ile ilgili terimlerin tanımlarını içerir.  
  
|Terim|Tanım|  
|----------|----------------|  
|Kod nesnesi|Visual Basic'te bir form arkasındaki modülü gibi adlandırılmış bir öğesiyle ilişkilendirilmiş komut dosyası altyapısı tarafından oluşturulan bir örnek veya adlandırılmış bir öğesiyle ilişkili bir C++ sınıfı. Tercihen, ana bilgisayar veya başka bir komut dosyası olmayan varlık kod nesnesi işleyebileceğiniz şekilde OLE Otomasyon destekleyen bir OLE Bileşen Nesne Modeli (COM) nesne budur.|  
|Adlandırılmış öğesi|Bir OLE COM nesnesi (tercihen OLE Otomasyon destekler) ana bilgisayar komut dosyasına ilginç uymak açısından gerekli olduğunu olduğunu. Örnek bir Web tarayıcısı ve belge ve Microsoft Word iletişim kutuları HTML sayfası ve tarayıcı verilebilir.|  
|Komut Dosyası|Komut dosyası altyapısı çalıştırılan programı yapar veriler. Bir komut dosyası bloklarını bir metin parçaları dahil olmak üzere tüm bitişik bir yürütülebilir veri olabilir `pcode`, hatta makineye özgü yürütülebilir bayt kodları. Bir ana bilgisayara bir komut dosyası komut dosyası altyapısı biri aracılığıyla yükler `IPersist*` arabirimleri aracılığıyla veya [Iactivescriptparse](../winscript/reference/iactivescriptparse.md) arabirimi.|  
|Komut dosyası altyapısı|Komut dosyaları işler OLE nesne. Bir komut dosyası motoru uygulayan [IActiveScript](../winscript/reference/iactivescript.md) ve isteğe bağlı olarak [Iactivescriptparse](../winscript/reference/iactivescriptparse.md) arabirimleri.|  
|Komut dosyası|Uygulama ya da Windows komut dosyası altyapısı sahibi program. Ana bilgisayar uygulayan [Iactivescriptsite](../winscript/reference/iactivescriptsite.md) ve isteğe bağlı olarak [Iactivescriptsitewindow](../winscript/reference/iactivescriptsitewindow.md) arabirimleri.|  
|Kod oluşturma yöntemi|Aracılığıyla bir nesneye iliştirilmiş bir komut dosyası bir kısmı [Iactivescriptparse](../winscript/reference/iactivescriptparse.md) arabirimi. Kod parçacıklarını toplam koleksiyonunu komut dosyasıdır.|  
|Komut dosyası dili|Bir komut dosyası yazılı (VBScript, örneğin) ve bu dil semantiği olduğu dili.|  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Windows komut dosyası arabirimleri](../winscript/windows-script-interfaces.md)