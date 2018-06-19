---
title: Test aracıları yükleyin ve Visual Studio için test denetleyicileri
ms.date: 03/02/2018
ms.prod: visual-studio-dev15
ms.technology: vs-ide-test
ms.topic: conceptual
helpviewer_keywords:
- configure test agents, test lab
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 20570d0a2d0173ca2322cb6ab1e888c7335cb4c0
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/26/2018
ms.locfileid: "31972111"
---
# <a name="install-test-agents-and-test-controllers"></a>Test denetleyicileri ve test aracılarını yükleme

Visual Studio ve Visual Studio Team Services (VSTS) veya Team Foundation Server (TFS) kullanan test senaryoları için bir test denetleyicisi gerekmez. Visual Studio için aracıları VSTS veya TFS ile iletişim kurarak düzenleme işleyin. Senaryo yapı için sürekli testleri çalıştırın ve VSTS veya TFS iş akışlarında yayın olabilir.

Kullanmak daha iyi olup olmadığını de düşünebilirsiniz [oluşturabilir veya yayın Yönetimi](use-build-or-rm-instead-of-lab-management.md) yerine Laboratuvar Yönetimi.

## <a name="system-requirements"></a>Sistem gereksinimleri

| Öğe | Gereksinimler |
| ---- | ------------ |
| **Aracı** | Windows 10<br />Windows 8, Windows 8.1<br />Windows 7 Service Pack 1<br />Windows XP Hizmet Paketi 3<br />Windows Server 2012, Windows Server 2012 R2<br />Windows Server 2008 Release 2, Service Pack 1 |
| **Denetleyici** | Windows 10<br />Windows 8, Windows 8.1<br />Windows 7 Service Pack 1<br />Windows Server 2012, Windows Server 2012 R2<br />Windows Server 2008 Release 2, Service Pack 1 |
| **.NET Framework** | .NET Framework 4.5 |

## <a name="install-the-test-controller-and-test-agents"></a>Test denetleyicisi ve test aracılarını yükleme

Aracılar için Visual Studio 2017 ' indirebilirsiniz [visualstudio.com](https://www.visualstudio.com/downloads/?q=agents). Sayfanın alt kısmına kaydırın ve Ara *aracılar için Visual Studio 2017*. Şunlardan birini seçin *Aracısı* veya *denetleyicisi*ve ardından *karşıdan*. Test aracısı veya denetleyicisi yüklemek için karşıdan yüklenen yürütülebilir dosyayı çalıştırmak.

Visual Studio 2015 ve Visual Studio 2013 için aracıları yükleyebilirsiniz [eski yüklemeleri](https://www.visualstudio.com/vs/older-downloads/) sayfası.

Bu yükleyiciler, sanal makinelerde kolay yükleme için ISO dosyaları olarak kullanılabilir.

## <a name="compatible-versions-of-tfs-microsoft-test-manager-the-test-controller-and-test-agent"></a>TFS, Microsoft Test Yöneticisi'ni, test denetleyicisi ve test aracısı uyumlu sürümleri

TFS, Microsoft Test Yöneticisi'ni (MTM), test denetleyicisi ve test aracısı farklı sürümleri aşağıdaki tabloya göre karıştırabilirsiniz:

| TFS | MTM Laboratuvar Merkezi ile | Denetleyici | Aracı |
| --- | -------------------------------------- | ---------- | ----- |
| 2017: 2015'den yükseltme veya yeni yükleyin | 2017 | 2017 | 2017 |
| 2017: 2015'den yükseltme veya yeni yükleyin | 2017 | 2013 güncelleştirme 5 | 2013 güncelleştirme 5 |
| 2017: 2015'den yükseltme veya yeni yükleyin | 2015 | 2013 güncelleştirme 5 | 2013 güncelleştirme 5 |
| 2015: 2013'den yükseltme | 2013 | 2013 |2013 |
| 2015: yeni bir yükleme | 2013 | 2013 | 2013 |
| 2015: 2013'den yükseltme veya yeni yükleyin | 2015 | 2013 | 2013 |
| 2013 | 2015 | 2013 | 2013 |

## <a name="upgrade-from-visual-studio-2013-test-agents"></a>Visual Studio 2013 test aracılarını yükseltme

Tüm yeni otomatikleştirilmiş test senaryolarda Visual Studio için aracıları kullanmanızı öneririz. Kullanabileceğiniz *Test aracıları dağıtmak* test aracılarını makinenize yükleyip için derleme tanımını görevi.

Aşağıdaki tabloda, Visual Studio 2013 için aracıları ve alternatifleri Team Foundation Server (TFS) 2015 ve VSTS tarafından desteklenen senaryolar gösterilmektedir:

| Visual Studio 2013 için aracıları tarafından desteklenen senaryolar | TFS ve VSTS alternatif |
| --- | --- |
| Visual Studio'da derleme, dağıtma, Test iş akışı | Kullanıcılar bir [yapı tanımı](/vsts/build-release/) (XAML derleme değil) için derleme, dağıtma ve testi senaryolarında TFS'de. |
| (Performans testi) sınama yük kullanarak uzak makineleri şirket içi | Kullanım Test denetleyicisi ve Test aracıları 2013 güncelleştirme 5 yük testleri şirket içi çalıştırmak için. |
| Otomatikleştirilmiş testleri Microsoft Test laboratuvarı ortamı kullanarak yöneticisinden, uzaktan yürütme | Şu anda bu senaryo için hiçbir seçenek yoktur. İşlevsel Testleri Çalıştır görev derlemede kullanma ve yayın tanımları (XAML derlemede değil) öneririz testleri uzaktan yürütün. |
| Geliştiriciler Visual Studio uzaktan testleri çalıştırma | Artık desteklenmemektedir. |
