---
title: "Proje bir Visual Basic hata ayıklama yapılandırması için ayarları | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vbProjectPropertiesDebug
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords:
- project settings [Visual Studio], debug configurations
- debug builds, project settings
- debugging [Visual Basic], debugger settings
- projects [Visual Studio], debug configurations
- project configurations, debug
- debug configurations, Visual Basic
ms.assetid: 72a8483a-af0b-4403-8b0d-ee9ad71ee435
caps.latest.revision: "17"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: a9d9b9c5cee3dc69698320af77a7cc909b344a2d
ms.sourcegitcommit: bd16e764134c436d2d2f46490f51234d5246ee50
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/22/2018
---
# <a name="project-settings-for-a-visual-basic-debug-configuration"></a>Visual Basic Hata Ayıklama Yapılandırması Proje Ayarları
Proje ayarlarını değiştirebileceğiniz bir [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)] hata ayıklama yapılandırmasını da **özellik sayfaları** anlatıldığı gibi penceresi [hata ayıklama ve dağıtım yapılandırmalarını](../debugger/how-to-set-debug-and-release-configurations.md). Aşağıdaki tablolarda hata ayıklayıcı gizlilikle ilgili ayarların nerede bulacağını Göster **özellik sayfaları** penceresi.  
  
> [!WARNING]
>  Bu konu, UWP uygulamaları için geçerli değil. Bkz: [(VB, C#, C++ ve XAML) bir hata ayıklama oturumu Başlat](../debugger/start-a-debugging-session-for-a-store-app-in-visual-studio-vb-csharp-cpp-and-xaml.md)  
  
### <a name="debug-tab"></a>Hata ayıklama sekmesi  
  
|Ayar|Açıklama|  
|-------------|-----------------|  
|**Yapılandırma**|Uygulamayı derlemek için modunu ayarlar. Arasından seçim **etkin (hata ayıklama)**, **hata ayıklama**, **sürüm**, **tüm yapılandırmaları**.|  
|**Eylemi Başlat**|Bu denetimler Debug menüsünden Başlat'ı seçtiğinizde gerçekleşecek eylemi belirtir.<br /><br /> -   **Proje başlangıç** varsayılandır ve hata ayıklama için başlangıç projesi başlatır. <br />-   **Dış program Başlat** başlatmak ve değil bir program eklemek sağlar parçası bir [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] projesi. Daha fazla bilgi için bkz: [eklemek için çalışan işlemler](../debugger/attach-to-running-processes-with-the-visual-studio-debugger.md).<br />-   **URL'de tarayıcı başlatmak** bir Web uygulaması ayıklamanızı sağlar.|  
|**Komut satırı bağımsız değişkenleri**|Ayıklanacak programı için komut satırı bağımsız değişkenlerini belirtir. Komut adı başlangıç dış programında belirtilen program adıdır. Eylemi Başlat Başlat URL'sine ayarlarsanız, komut satırı bağımsız değişkenleri göz ardı edilir.|  
|**Çalışma dizini**|Ayıklanacak programın çalışma dizinini belirtir. İçinde [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)], çalışma dizini uygulama başlatılan dizindir. Varsayılan çalışma dizini \bin\Debug ya da geçerli yapılandırmasına bağlı olarak \bin\Release bağlıdır.|  
|**Uzak makine kullanın**|Uzaktan hata ayıklama, onay kutusu seçili olduğunda etkindir. Metin kutusuna hata ayıklama amacıyla burada uygulamanın çalışacağı uzak makine adını yazın veya bir [Msvsmon sunucu adı](../debugger/remote-debugging.md). Uzak makinedeki EXE konumunu yapı sekmesini çıkış yolu özelliğinde belirtilir. Konumun uzak makinede paylaşılabilir bir dizin olmalıdır.|  
|**Yönetilmeyen kod hata ayıklama**|Yerel (yönetilmeyen) Win32 kod çağrıları yönetilen uygulamanızdan ayıklamanızı sağlar. Bu hata ayıklayıcı türü için karma seçme ile aynı etkiye sahip bir [!INCLUDE[vcprvc](../code-quality/includes/vcprvc_md.md)] projesi.|  
|**SQL Server hata ayıklama**|SQL Server veritabanı nesneleri hata ayıklama sağlar.|  
  
### <a name="compile-tab-press-advanced-compile-options-button"></a>Sekme derleme: derleme seçenekleri Gelişmiş düğmesine basın  
  
|Ayar|Açıklama|  
|-------------|-----------------|  
|**En iyi duruma getirme etkinleştir**|Bu seçenek işaretinin kaldırılması gerekir. En iyi duruma getirme neden görülen kaynak kodundan farklı olması gerçekte yürütülen kod [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]ve böylece hata ayıklama zorlaştırır. İyileştirilmiş kodda, simgeler olmayan yüklenmiş varsayılan olarak sadece kendi kodumu ile hata ayıklama sırasında.|  
|**Hata ayıklama bilgileri üret**|Hata ayıklama ve yayın varsayılan olarak tanımlanan sürümleri, bu (/ debug derleyici seçeneği eşdeğer) ayarı oluşturur hata ayıklama bilgileri derleme zamanında. Hata ayıklayıcı değişken adları ve diğer bilgileri, ayıklarken yararlı bir biçime göstermek için bu bilgileri kullanır. Bu bilgiler olmadan programınızı derleme yaparsanız, hata ayıklayıcı işlevi sınırlı olacaktır. Daha fazla bilgi için bkz: [/debug](/dotnet/visual-basic/reference/command-line-compiler/debug).|  
|**Hata ayıklama sabiti tanımlayın**|Bu simge tanımlama etkinleştirir çıkış işlevlerin koşullu derleme [hata ayıklama sınıfı](/dotnet/api/system.diagnostics.debug). Tanımlanan bu simge ile hata ayıklama sınıfı yöntemlerinin çıkışı oluşturmak [çıktı penceresi](../ide/reference/output-window.md). Bu simgenin olmadan hata ayıklama sınıfı yöntemleri derlenmemiş ve hiçbir çıktı oluşturulur. Bu simge hata ayıklama sürümünü tanımlanır ve yayın sürümünde tanımlı değil. Bu simgeyi bir sürümde tanımlama programınızı yavaşlar gereksiz kod oluşturur.|  
|**İzleme sabiti tanımlayın**|Bu simge tanımlama etkinleştirir çıkış işlevlerin koşullu derleme [izleme sınıfı](/dotnet/api/system.diagnostics.trace.aspx). Tanımlanan bu simgesiyle izleme sınıf yöntemlerini çıkışı oluşturmak [çıktı penceresi](../ide/reference/output-window.md). Bu simgenin olmadan izleme sınıfı yöntemleri derlenmemiş ve İzleme çıkışı oluşturulur. Bu simge, hata ayıklama ve yayın sürümleri için varsayılan olarak tanımlanır.|  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Hata ayıklayıcı ayarları ve hazırlığı](../debugger/debugger-settings-and-preparation.md)