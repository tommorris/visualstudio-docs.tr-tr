---
title: "Proje türü tasarım kararları | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- project types, project file persistence
- project types, commitment mechanics
- project types, items
- project types, design decisions
ms.assetid: f68671fe-fd7a-4e56-a0b5-330b0f1fedb1
caps.latest.revision: "10"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: ce1de0467e7e662fd0def096ef6adb042578f8b7
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="project-type-design-decisions"></a>Proje türü tasarım kararları
Yeni bir proje türü oluşturmadan önce proje türü ile ilgili bazı tasarım kararlarını olmanız gerekir. Hangi tür projelerinizi içerecek öğeleri, proje dosyalarını kalıcı nasıl ve ne taahhüt modeli kullanacağınıza karar vermeniz gerekir.  
  
## <a name="project-items"></a>Proje öğeleri  
 Projenizi dosyaları veya soyut nesneleri kullanacak mısınız? Dosyaları kullanırsanız, başvuru veya dizin tabanlı dosyaları olacak mı? Yerel veya uzak olarak dosyaları veya soyut nesnelere giderek misiniz?  
  
 Proje öğeleri, dosyaları veya Internet üzerinden veritabanı deposu veya veri bağlantıları nesneleri gibi daha soyut nesneler olabilir. Öğeleri dosyalar olduğunda, proje başvurusu tabanlı veya bir dizin tabanlı proje olabilir.  
  
 Başvuru tabanlı projelerde öğeleri birden çok projede yer alabilir. Ancak, bir öğeyi temsil eden gerçek dosya yalnızca bir dizinde bulunur. Dizin tabanlı projelerde tüm proje öğeleri dizin yapısında mevcut. Daha fazla bilgi için bkz: [NIB: öğesi yönetimi projelerinde](http://msdn.microsoft.com/en-us/762e606b-7f44-4b66-97a1-e30a703654a0).  
  
 Yerel öğeler, uygulamanın yüklü olduğu bilgisayarda depolanır. Uzak öğeleri, bir yerel ağda ayrı bir sunucuda veya başka bir yerde Internet'te depolanabilir.  
  
## <a name="project-file-persistence"></a>Proje dosyası kalıcılığı  
 Ortak düz dosya sistemleri veya yapılandırılmış depolama verilerinin depolanacağı? Standart Düzenleyici ya da bir projeye özgü düzenleyici kullanarak dosyaları açılacak?  
  
 Verilerini kalıcı hale getirmek için çoğu uygulama verilerini bir dosyaya kaydedin ve kullanıcı geri gerekir veya gözden geçirme bilgi değiştirdiğinizde okuyun.  
  
 Tek bir dosyada kalıcı verilerini depolamak üzere birkaç Bileşen Nesne Modeli (COM) nesneleri ihtiyacınız olduğunda bileşik dosyalar olarak da bilinir yapılandırılmış depolama genellikle kullanılır. Yapılandırılmış depolama ile birkaç farklı yazılım bileşenleri tek disk dosya paylaşabilir.  
  
 Projenizdeki öğeleri kalıcılığını ilgili olarak dikkate alınması gereken birkaç seçeneğiniz vardır. Aşağıdaki seçeneklerden birini gerçekleştirebilirsiniz:  
  
-   Değiştirildi, tek tek her dosyayı kaydedin.  
  
-   Pek çok işlem tek bir yakalama **kaydetmek** işlemi.  
  
-   Dosyaları yerel olarak kaydedin ve ardından bir sunucuya yayımlayın veya uzak bir nesne bir veri bağlantısı öğeyi temsil ettiğinde proje öğeleri kaydetmek için başka bir yaklaşım kullanın.  
  
 Kalıcılık hakkında daha fazla bilgi için bkz: [proje kalıcılığı](../../extensibility/internals/project-persistence.md) ve [açma ve kaydetme proje öğeleri](../../extensibility/internals/opening-and-saving-project-items.md).  
  
## <a name="project-commitment-model"></a>Proje taahhüt modeli  
 Kalıcı veri nesneleri açılacak doğrudan modu veya hizmetteki modunda?  
  
 Veri nesneleri doğrudan modunda açıldığında, verilere yapılan değişiklikleri hemen veya kullanıcı dosyayı el ile kaydettiğinde dahil edilmiştir.  
  
 Veri nesneleri, işlenen modunu kullanarak açıldığında değişiklikler bellekte geçici bir konuma kaydedilir ve kullanıcı el ile dosyayı kaydetmeyi seçerse kadar iletilmez. Bu sırada, tüm değişiklikleri birlikte olmalıdır veya hiçbir değişiklik yapılmaz.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Denetim listesi: Yeni proje türleri oluşturma](../../extensibility/internals/checklist-creating-new-project-types.md)   
 [NIB: öğesi yönetimi projelerine](http://msdn.microsoft.com/en-us/762e606b-7f44-4b66-97a1-e30a703654a0)   
 [Açıp kaydederek proje öğeleri](../../extensibility/internals/opening-and-saving-project-items.md)   
 [Proje kalıcılığı](../../extensibility/internals/project-persistence.md)   
 [Proje modeli öğeleri](../../extensibility/internals/elements-of-a-project-model.md)   
 [Proje modeli çekirdek bileşenleri](../../extensibility/internals/project-model-core-components.md)   
 [Proje Türleri Oluşturma](../../extensibility/internals/creating-project-types.md)