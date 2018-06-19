---
title: Visual Studio hata ayıklayıcısı sözlüğü | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- glossary [Debugging SDK]
- debugging [Debugging SDK], glossary
ms.assetid: 4a2cfaab-1fbd-4a23-bd00-9ac4cc50d7fd
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 088f5d5a6b1edfc218b5dbe291d957d903f79702
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
ms.locfileid: "31128195"
---
# <a name="visual-studio-debugger-glossary"></a>Visual Studio hata ayıklayıcısı sözlüğü
İçinde kullanılan terimleri şunlardır [!INCLUDE[vsprvs](../../../code-quality/includes/vsprvs_md.md)] hata ayıklama SDK.  
  
## <a name="terms"></a>Koşulları  
 ilişkili kesme noktası  
 Kodda kesme için bir Özet. İlişkili bir kesme noktası ve bir kesme noktası yönerge kodu akışında arasında bire bir ilişki yoktur. Ne zaman bellekten kod, ilişkili kesme noktaları bağlantısını.  
  
 causality  
 Birden çok fiziksel iş parçacıkları, işlemleri ve makine mantıksal bir iş parçacığı yürütme izlemek ve o mantıksal iş parçacığı verilen herhangi bir noktada çağrı yığınını parçacığının yaşam süresi yeniden olanak sağlar.  
  
 kod bağlamı  
 Kodda hata ayıklama altyapısı tarafından tanınan bir konumdaki bir Özet sağlar. Çalışma zamanı mimari için bir kod bağlamı bir programın yönerge akışında bir adresidir. Hangi kod yönergeleri tarafından temsil edilebilir değil nontraditional diller için bir kod bağlamı başka yollarla temsil edilebilir.  
  
 kod yolu  
 Burada bir dal alınır veya bir işlev çağrısı yapıldığında kodda yürütme noktasını temsil eder. Yığın izlemesi temelde işlevi çağrısı kod yolları bir listesidir.  
  
 hata ayıklama altyapısı (DE)  
 Bir çalışma zamanı mimarisi hata ayıklama sağlayan bileşeni. Hata ayıklama altyapısı yorumlayıcı veya işletim sistemi ile birlikte çalışır ve yürütme denetimi, kesme noktaları ve ifade değerlendirme gibi hata ayıklama hizmetleri sağlar.  
  
 Belge bağlamı  
 Hata ayıklama altyapısı tarafından tanınan bir kaynak dosya belgedeki herhangi bir konumdaki bir Özet sağlar. Çoğu diller için bir belge içeriği, bir kaynak dosyasında konumdur. Kaynak dosyasını bir metin olmayabilir nontraditional diller için başka bir şekilde bir belge bağlamı temsil edilebilir. Ayrıca bkz. *belge konumu*.  
  
 Belge konumu  
 IDE bilinen bir kaynak dosyasında herhangi bir konumdaki bir Özet sağlar. Çoğu diller için bir kaynak dosya konumunda bir belge konumdur. Nontraditional diller için diğer yollarla belge konumu temsil edilebilir. Ayrıca bkz. *belge bağlamı*.  
  
 hata kesme  
 Bekleyen bir kesme noktası hata açıklamak için bir Özet. Bir hata kesme noktası bekleyen kesme veya bekleyen kesme noktası bağlamanın dışında bir kod konuma engelleyen diğer bilgileri ilişkili ifade bekleyen kesme noktası konumunu hata açıklayabilir.  
  
 Değerlendirme bağlamı  
 İfade değerlendirme için bir programlama bağlamı için bir Özet sağlar. Genellikle, bir değerlendirme bağlamı bir kapsamı değil. İfade değerlendirme bir ifade bağlamda yaparken ifade bağlam oluşturma noktaya eşleşen kapsam kuralları sağlar. Örneğin, bir yığın çerçevesinde oluşturulan bir ifade bağlamı, yerel değişkenler, yöntem parametreleri, sınıf üyeleri (varsa) ve genel değişkenler değerlendirmesi için bağlam sağlayacaktır.  
  
 ele geçirilen özel durumu  
 Hiçbir özel durum mekanizması işleme geçerli yığın çerçevesini yerinde olsa bile, hata ayıklama altyapısı tarafından müdahale bir özel durum.  
  
 JustMyCode  
 Yalnızca bir kullanıcıya ait kodda hata ayıklama ve sistem kodu gibi tüm ara kodu yoksayılıyor kavramı — kaynak kodu, sistem kodunu kullanılabilir olsa bile.  
  
 bekleyen kesme noktası  
 Önce sırasında ve sonrasında kesme noktaları için bir Özet sağlar kodudur yüklenir ve kesme noktaları sanallaştırmak için yol. Kesme noktası bekleyen bir:  
  
-   Bir veya daha fazla program kodunda kesme noktası bağlamak için gerekli tüm bilgileri içerir.  
  
-   Bir veya daha fazla program birden fazla kod konumda bağlar.  
  
-   Hiçbir zaman kendisini kodu bağlar.  
  
 Her zaman kodu yükler, bir programda tüm bekleyen kesme noktaları bunlar bağlayabilirsiniz olmadığını görmek için denetlenir. Bekleyen bir kesme noktası onu bağlar tüm ilişkili kesme noktaları içeren kabul edilir.  
  
 process  
 Fiziksel bir Win32 işlem. Bir işlem birden çok programları içerebilir. Ayrıca bkz. *program*.  
  
 program  
 İçinde belirli bir çalışma zamanı mimarisi çalıştıran tek bir ad. Ayrıca bkz. *işlem*.  
  
 oturum hata ayıklama Yöneticisi (SDM)  
 Herhangi bir sayıda makineler herhangi bir sayıda birden çok işlemi programlarında hata ayıklamayı debug motorları herhangi bir sayıda yönetir. Temel düzeyde SDM çoğaltıcı hata ayıklama altyapısını olur. Ayrıca, SDM IDE hata ayıklama oturumu birleşik bir görünümünü sağlar.  
  
 yığın çerçevesi  
 Belirli bir kareye hesaplama durumunu ve iç içe işlev çağrılarına belirli düzeyde temsil eder.  
  
 thread  
 En az bir programda yığın tabanlı yönerge yürütme genelleştirilmiş kavramı vardır.  
  
 Uyarı kesme noktası  
 Uyarı bekleyen bir kesme noktası olarak tanımlamak için bir Özet. Bir uyarı kesme noktası neden bekleyen kesme noktası henüz bir kod konuma bağlı olmayan bir nedeni açıklanmaktadır. Bu kod henüz bekleyen kesme noktası tarafından açıklanan konumu ya da başka bir nedenle yükledi değil emin olabilir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Visual Studio Hata Ayıklayıcı Genişletilebilirliği](../../../extensibility/debugger/visual-studio-debugger-extensibility.md)