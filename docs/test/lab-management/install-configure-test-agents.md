---
title: "Yükleme ve test aracılarını yapılandırma | Microsoft Docs"
ms.custom: 
ms.date: 05/02/2017
ms.reviewer: 
ms.suite: 
ms.technology: vs-devops-test
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: configure test agents, test lab
ms.assetid: EBAA2E04-A97A-4047-B739-8DBA7F2D5074
caps.latest.revision: "56"
ms.author: douge
manager: douge
ms.workload: multiple
ms.openlocfilehash: 15a2852d657e1c10652d99c25401db5ab76a2feb
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="install-and-configure-test-agents"></a>Yükleme ve test aracılarını yapılandırma

Aracılar için Microsoft Visual Studio Team Services veya TFS ile iletişim kurarak düzenleme işlediğinden, Visual Studio ve Visual Studio Team Services veya Team Foundation Server (TFS) kullanarak test senaryoları için bir test denetleyicisi gerekmez. Örneğin, sürekli test, yapı ile çalıştırıyorsanız ve Team Services veya TFS iş akışlarında bırakın.

Test aracısı veya test denetleyicisi TFS 2013 ile çalışmak için ihtiyacınız varsa, Microsoft Visual Studio 2013 güncelleştirme 5 aracıları kullanın ve test denetleyicisi yapılandırın.

Ayrıca, daha kolay olacaktır, göz önünde bulundurun [derleme veya yayın Yönetimi kullanmanız](use-build-or-rm-instead-of-lab-management.md).

## <a name="what-do-i-need"></a>Ne yapmalıyım?

**Burada test denetleyicisi alabilir ve test aracıları?**

* Yapı vNext görevlerini kullanarak testleri çalıştırma ve yerel bir dizinden aracıları yüklemek istiyorsanız- 

  * [Karşıdan yükleme aracıları için Microsoft Visual Studio 2015 RTM ve güncelleştirme 1](http://go.microsoft.com/fwlink/p/?LinkId=619266). 

  * [Microsoft Visual Studio 2017 ve Visual Studio 2015 güncelleştirme 2 için aracıları indirme](https://www.visualstudio.com/downloads/download-visual-studio-vs) -seçin **araçları Visual Studio 2015 için** ve ardından **Visual Studio 2015 için aracıları** soldan Gezinme çubuğu.

* [Microsoft Visual Studio 2013 güncelleştirme 5 için aracıları Yükle](http://go.microsoft.com/fwlink/p/?LinkId=619264), çalıştırmak istiyorsanız:

  * Yük testleri şirket içi uzak makineleri kullanma.

  * Microsoft Test Yöneticisi'ni veya mstest'i ve test ayarlarını kullanarak uzaktan laboratuvar ortamları için sürekli sınar.

  * TFS 2013 kullanarak sürekli testleri.

Bu yükleyiciler, sanal makinelerde kolay yükleme için ISO dosyaları (sanal CD) olarak kullanılabilir. 

[TFS, Microsoft Test Yöneticisi'ni, test denetleyicisi ve test aracısı sürümleri karıştırabilir miyim?](#MixedVersions)

**My test denetleyicisi ve test aracıları yüklemek hangi sistem gereksinimleri gerekiyor?**

| Öğe | Gereksinimler |
| ---- | ------------ |
| **Aracı** | Windows 10<br />Windows 8, Windows 8.1<br />Windows 7 Service Pack 1<br />Windows XP Hizmet Paketi 3<br />Windows Server 2012, Windows Server 2012 R2<br />Windows Server 2008 Release 2, Service Pack 1 |
| **Denetleyici** | Windows 10<br />Windows 8, Windows 8.1<br />Windows 7 Service Pack 1<br />Windows Server 2012, Windows Server 2012 R2<br />Windows Server 2008 Release 2, Service Pack 1 |
| **.NET Framework** | .NET Framework 4.5 |

## <a name="q--a"></a>Soru - Yanıt

<!-- BEGINSECTION class="m-qanda" -->

<a name="MixedVersions"></a>

####<a name="q-can-i-mix-versions-of-tfs-microsoft-test-manager-the-test-controller-and-test-agent"></a>S: TFS, Microsoft Test Yöneticisi'ni, test denetleyicisi ve test aracısı sürümleri karışık?

A: Evet uyumlu ve desteklenen birleşimleri şunlardır:

| TFS | Microsoft Test Yöneticisi ile Laboratuvar Merkezi | Denetleyici | Aracı |
| --- | -------------------------------------- | ---------- | ----- |
| 2015: 2013'den yükseltme | 2013 | 2013 |2013 |
| 2015: yeni bir yükleme | 2013 | 2013 | 2013 |
| 2015: 2013'den yükseltme veya yeni yükleyin | 2015 | 2013 | 2013 |
| 2013 | 2015 | 2013 | 2013 |

####<a name="q-will-the-test-agent-2015-support-all-the-scenarios-supported-by-test-controller-and-test-agent-of-visual-studio-2013"></a>S: Test aracısı 2015 Test denetleyicisi ve Test aracısı, Visual Studio 2013 tarafından desteklenen tüm senaryoları destekleyecek mi?

Y:, aracıları Visual Studio için tüm yeni otomatikleştirilmiş test senaryoları kullanmanızı öneririz. Test aracıları makinenize yükleyip için bir derleme tanımınız Test aracıları dağıtmak görevini kullanabilirsiniz.
Aşağıdaki tabloda, aracıları tarafından Visual Studio 2013 ve alternatifleri için Team Foundation Server (TFS) 2015 ve Team Services (TS) için desteklenen senaryolar gösterilmektedir.

| Visual Studio 2013 için aracıları tarafından desteklenen senaryolar | TFS ve TS alternatif |
| --- | --- |
| Visual Studio'da derleme, dağıtma, Test iş akışı | Kullanıcılar bir [yapı tanımı](https://www.visualstudio.com/team-services/continuous-integration/) (XAML derleme değil) için derleme, dağıtma ve testi senaryolarında TFS'de. |
| (Performans testi) sınama yük kullanarak uzak makineleri şirket içi | Yük testleri şirket içi çalıştırmak için test denetleyicisi ve Test aracıları 2013 güncelleştirme 5 kullanın. [Daha fazla bilgi](https://msdn.microsoft.com/en-us/library/ff400223.aspx). |
| Otomatikleştirilmiş testleri Microsoft Test laboratuvarı ortamı kullanarak yöneticisinden, uzaktan yürütme | Şu anda bu senaryo için hiçbir seçenek yoktur. İşlevsel Testleri Çalıştır görev derlemede kullanma ve yayın tanımları (XAML derlemede değil) öneririz testleri uzaktan yürütün. |
| Geliştiriciler Visual Studio uzaktan testleri çalıştırma | Artık desteklenmemektedir. |

<!-- ENDSECTION -->

## <a name="see-also"></a>Ayrıca bkz.

* [Makineleri ayarlama ve Test ayarlarını kullanarak tanılama bilgisi toplama](https://msdn.microsoft.com/library/dd286743%28v=vs.140%29.aspx)
