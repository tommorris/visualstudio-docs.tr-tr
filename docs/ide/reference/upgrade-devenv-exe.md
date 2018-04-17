---
title: -Yükseltme (devenv.exe) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-general
ms.topic: conceptual
helpviewer_keywords:
- /upgrade Devenv switch
- Devenv, /upgrade switch
- upgrade Devenv switch
ms.assetid: 3468045c-5cc9-4157-9a9d-622452145d27
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 66a28d534c9b3fa019849ac8a3ecd42b0ad7e6ff
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="upgrade-devenvexe"></a>/Upgrade (devenv.exe)
Çözüm dosyasını ve tüm proje dosyalarını veya, geçerli belirtilen proje dosyası güncelleştirmeleri [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] bu dosyalar için biçimleri.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
devenv SolutionFile | ProjectFile /upgrade  
```  
  
## <a name="arguments"></a>Arguments  
 `SolutionFile`  
 Çözümün tamamında ve projeleri yükseltiyorsanız gereklidir. Yol ve çözüm dosya adı. Yalnızca çözüm dosyasını veya adı bir tam yol ve çözüm dosyasının adını girebilirsiniz. Adlı dosyayı veya klasörü henüz mevcut değilse, oluşturulur.  
  
 `ProjectFile`  
 Tek bir proje yükseltiyorsanız gereklidir. Yol ve çözüm içinde proje dosyasının adı. Yeni proje dosyası veya bir tam yol adı ve proje dosyası adını girebilirsiniz. Adlı dosyayı veya klasörü henüz mevcut değilse, oluşturulur.  
  
## <a name="remarks"></a>Açıklamalar  
 Yedeklemeleri otomatik olarak oluşturulur ve geçerli dizinde oluşturulan yedekleme adlı bir dizine kopyalanır.  
  
 Yükseltilebilmesi için önce kaynak denetimli çözümleri veya projeleri kullanıma alınması gerekir.  
  
 Kullanarak `/upgrade` anahtar başlamıyor [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)]. Yükseltme sonuçlarını, proje ve çözüm geliştirme dilini yükseltme raporunda görülebilir. Hiçbir hata ya da kullanım bilgilerini döndürülür. Proje yükseltme hakkında daha fazla bilgi için [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)], bkz: [bağlantı noktası, geçirme ve yükseltme Visual Studio projeleri](../../porting/port-migrate-and-upgrade-visual-studio-projects.md).  
  
## <a name="example"></a>Örnek  
 Bu örnek için varsayılan klasörünüzde "MyProject.sln" adlı bir çözüm dosyasını yükseltir [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] çözümler.  
  
```  
devenv "MyProject.sln" /upgrade  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Devenv Komut Satırı Anahtarları](../../ide/reference/devenv-command-line-switches.md)