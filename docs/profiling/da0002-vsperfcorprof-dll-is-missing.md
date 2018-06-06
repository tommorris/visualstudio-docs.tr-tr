---
title: 'DA0002: VSPerfCorProf.dll eksik | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
f1_keywords:
- vs.performance.DA0002
- vs.performance.2
- vs.performance.rules.DAVsPerfCorProfMissing
- vs.performance.rules.DA0002
ms.assetid: 76e614b3-ad7e-4b92-b7be-88dc1329be1d
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: cc0207a529fe74e23e6b1b032c1eb6919cf38592
ms.sourcegitcommit: 58052c29fc61c9a1ca55a64a63a7fdcde34668a4
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/04/2018
ms.locfileid: "34749313"
---
# <a name="da0002-vsperfcorprofdll-is-missing"></a>DA0002: VSPerfCorProf.dll eksik
|||  
|-|-|  
|Kural Kimliği|DA0002|  
|Kategori|Profil oluşturma araçları kullanım|  
|Profil oluşturma yöntemleri|VSPerfCmd ve VSPerfASPNETCmd komut satırı araçlarını kullanarak profil oluşturma|  
|İleti|Dosyanın doğru ortam değişkenleri ayarlamadan toplanan göründüğü *VSPerfCLREnv.cmd*. Yönetilen ikili dosyaları simgelerini çözülebilir değildir.|  
|Kural türü|Bilgiler|  
  
## <a name="cause"></a>Sebep  
 Profil oluşturucu bulunamadı *VSPerfCorProf.dll* Çalıştır profili oluşturma sırasında. Profil Oluşturucu verilerin toplanması için komut satırı araçları kullanarak olmadan kullanıldığında, bu uyarıyı oluşur *VSPerfCLREnv.cmd* gerekli ortam değişkenlerini başlatmak için araç. Profil oluşturma araçları başlattığınızda başka bir profil oluşturucu çalışıyorsa, uyarı da tetikleyebilir.  
  
## <a name="rule-description"></a>Kural açıklaması  
 Özel ortam değişkenleri, bir profil oluşturma çalıştırma .NET Framework ikili dosyaları sembolleri çözümlemek profil oluşturucu için önce ayarlanmalıdır. Bu uyarı öneren *VSPerfCLREnv.cmd* aracı profil oluşturma verileri toplanan önce değil çalıştırıldı. Yönetilen ikili dosyaları simgelerini çözebilir değil. Komut satırından profil oluşturma araçlarını kullanma hakkında daha fazla bilgi için bkz: [komut satırından profil oluşturma](../profiling/using-the-profiling-tools-from-the-command-line.md)  
  
## <a name="how-to-fix-violations"></a>İhlallerini düzeltmek nasıl  
 Ne zaman, profil yönetilen uygulamalar komut satırı araçlarını kullanarak [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] profil çalıştırmak Araçları [VSPerfCLREnv](../profiling/vsperfclrenv.md) veri toplama başlamadan önce komut satırı aracı.