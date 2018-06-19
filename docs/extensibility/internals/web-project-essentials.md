---
title: Web projesi Essentials | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- web projects, essentials
ms.assetid: ca2f4e43-322c-4431-8680-52da846940bc
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 6918c539409a31dfe5249adb5858ca20c8c2337c
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
ms.locfileid: "31141001"
---
# <a name="web-project-essentials"></a>Web projesi temelleri
Web projeleri, Web uygulamaları oluşturun. Bir Web projesi akıllı Web sayfaları bir Web uygulaması oluşturmak için kullanabilirsiniz. Akıllı bir Web sayfasında isteğe bağlı Web sayfasını işler sunucu tarafı kodu vardır.  
  
 Geleneksel programlama dilleri gibi kullanılarak [!INCLUDE[vbprvb](../../code-quality/includes/vbprvb_md.md)] veya [!INCLUDE[csprcs](../../data-tools/includes/csprcs_md.md)], toplamak ve kullanıcıdan bilgi işlem, bir veritabanında depolamak ve benzeri için akıllı Web sayfaları oluşturabilirsiniz.  
  
-   Arka plan kod modeli bağımlı kaynak kodu dosyaları dosya uzantısı .aspx veya .asmx bulunan Web sayfaları ile ilişkilendirir. Örneğin, HelloWorld.aspx bağımlı kaynak kodu dosya hello.aspx.cs olabilir.  
  
-   Akıllı bir Web sayfası ile ilişkili sunucu tarafı kodu Web sitesi/bin klasöründeki yürütülebilir bir dosyanın derlenir.  
  
-   Belirli bir Web sayfası ile ilişkili olmayan yardımcı sınıfları gibi ek kaynak kodu dosyaları Web sitesi /App_Code klasöründe bulunur.  
  
    -   Bir Web sitesi projesini (WSP) Akıllı her Web sayfası için yürütülebilir bir dosya oluşturur. Ek yürütülebilir dosyalar hiçbir kaynak kodu dosyalarından /App_Code klasöründe oluşturulur.  
  
    -   Bir Web uygulaması projesi (WAP) /App_Code klasöründeki tüm kaynak dosyalarının yanı sıra tüm akıllı Web sayfaları için kod birleştirir tek bir yürütülebilir dosya oluşturur.  
  
-   Bir Web projesi için çözüm dosyası ayrı olarak Web sitesinin kendisinde bulunur. Varsayılan olarak, çözüm dosyalarını \Documents and Settings bulunan\\*YourAccount*\My belgeleri\\*\<Visual Studio ### >* \Projects\\ *YourWebSite*.  
  
    > [!NOTE]
    >  Web sitesi ile çözüm dosyasını tutmak istiyorsanız, yalnızca taşıyabilir vardır ve yeniden açın.  
  
-   Hiçbir çözüm dosyasını Visual Studio'da bir Web sitesi açarsanız, yeni bir çözüm dosyası için otomatik olarak oluşturulur.  
  
-   Web projeleri proje dosyalarını sahiptir. Proje bilgileri çözüm dosyasını, web.config dosyasını ve başka bir yerde depolanır.  
  
-   Genel Özellikler otomatik olarak bir Web projesine ekleme Web projesi çözüm klasöründe bir depolama dosyası oluşturur.  
  
-   Sayfa yönergesi kullanarak akıllı bir Web sayfasında sunucu tarafı programlama dili ile ilişkili olabilir veya \<komut dosyası runat = "server" > etiketi.  
  
-   Ayrıca, Web sayfaları herhangi bir sayıda istemci tarafı komut dosyası blokları herhangi komut dosyası dilinde yazılmış olabilir.  
  
-   Proje ve öğe şablonları ve kayıt ekleyerek Web sitesi proje sistemi uygulanan [!INCLUDE[vwprvw](../../extensibility/internals/includes/vwprvw_md.md)] projesi.  
  
-   WAP sistem proje türü olarak da adlandırılan bir proje alt uygulanır. [!INCLUDE[vwprvw](../../extensibility/internals/includes/vwprvw_md.md)] Proje WAP sistem oluşturmak için WAP alt türe göre özellikli. Proje alt türleri hakkında daha fazla bilgi için bkz: [proje Subtypes](../../extensibility/internals/project-subtypes.md).  
  
-   Akıllı bir Web sayfasında HTML bir sunucu tarafı programlama dili ile birleştirir. Sunucu tarafı dil kapsanan dil adı verilir. Kapsanan bir dil desteği için Web projesi sistemi uygulamalıdır <xref:Microsoft.VisualStudio.TextManager.Interop.IVsContainedLanguage> arabirimlerinin ailesi.  
  
    -   Bir düzenleyicide kapsanan dili desteklemek için HTML dil hizmeti bir kapsanan dil hizmeti kapsanan dil kodu görüntüleme erteleneceği gerekir.  
  
    -   Kod Düzenleyicisi'nin birincil arabellekte hata işaretçileri (kırmızı squigglies) her zaman oluşturulmalıdır.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Web Projeleri](../../extensibility/internals/web-projects.md)