---
title: 'DA0002: VSPerfCorProf.dll eksik | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-debug
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
ms.openlocfilehash: 9f0e1b87a4fb5232a949c2ec4f4c9d32594b3fb8
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="da0002-vsperfcorprofdll-is-missing"></a>DA0002: VSPerfCorProf.dll eksik
|||  
|-|-|  
|Kural Kimliği|DA0002|  
|Kategori|Profil oluşturma araçları kullanım|  
|Profil oluşturma yöntemleri|VSPerfCmd ve VSPerfASPNETCmd komut satırı araçlarını kullanarak profil oluşturma|  
|İleti|Dosyanın doğru VSPerfCLREnv.cmd ortam değişkenleri ayarlamadan toplanan görünür. Yönetilen ikili dosyaları simgelerini çözülebilir değildir.|  
|Kural türü|Bilgiler|  
  
## <a name="cause"></a>Sebep  
 Profil Oluşturucu VSPerfCorProf.dll profil çalışması sırasında bulunamadı. Profil Oluşturucu verilerin toplanması için komut satırı araçları gerekli ortam değişkenlerini başlatmak için VSPerfCLREnv.cmd aracını kullanarak olmadan kullanıldığında, bu uyarıyı oluşur. Profil oluşturma araçları başlattığınızda başka bir profil oluşturucu çalışıyorsa, uyarı da tetikleyebilir.  
  
## <a name="rule-description"></a>Kural Tanımı  
 Özel ortam değişkenleri, bir profil oluşturma çalıştırma .NET Framework ikili dosyaları sembolleri çözümlemek profil oluşturucu için önce ayarlanmalıdır. Bu uyarı, profil oluşturma verileri toplanan önce VSPerfCLREnv.cmd aracı çalıştırılmadı önerir. Yönetilen ikili dosyaları simgelerini çözebilir değil. Komut satırından profil oluşturma araçlarını kullanma hakkında daha fazla bilgi için bkz: [komut satırından profil oluşturma](../profiling/using-the-profiling-tools-from-the-command-line.md)  
  
## <a name="how-to-fix-violations"></a>İhlaller Nasıl Düzeltilir?  
 Ne zaman, profil yönetilen uygulamalar komut satırı araçlarını kullanarak [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] profil çalıştırmak Araçları [VSPerfCLREnv](../profiling/vsperfclrenv.md) veri toplama başlamadan önce komut satırı aracı.