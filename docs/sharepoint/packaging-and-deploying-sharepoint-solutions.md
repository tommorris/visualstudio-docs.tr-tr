---
title: Paketleme ve SharePoint çözümlerini dağıtma | Microsoft Docs
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
- VB
- CSharp
helpviewer_keywords:
- packaging [SharePoint development in Visual Studio]
- deploying [SharePoint development in Visual Studio]
- SharePoint development in Visual Studio, packaging and deploying
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: 2421a1f39f2969563bc10a43367936ae499fac30
ms.sourcegitcommit: d9e4ea95d0ea70827de281754067309a517205a1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/29/2018
ms.locfileid: "37120458"
---
# <a name="package-and-deploy-sharepoint-solutions"></a>Paket ve SharePoint çözümlerini dağıtma
  Genellikle, bir SharePoint çözüm, bir çözüm paketi (.wsp) dosyası kullanarak bir SharePoint sunucusuna dağıtılır. SharePoint Proje öğeleri özelliklerini düzenlemek ve SharePoint özelliklerinizi dağıtmak üzere paket oluşturmak için Visual Studio'yu kullanabilirsiniz.  
  
 Bu konuda, aşağıdaki bilgiler sağlanmaktadır:  
  
-   [Özellikleri ve paketleri oluşturma](#Creating)  
  
-   [Özellik ve aracı desteği paketleme](#Tools)  
  
-   [SharePoint çözümlerini dağıtma](#Deploying)  
  
-   [SharePoint çözümlerini dosyalarında dağıtma](#DeployingFiles)  
  
## <a name="create-features-and-packages"></a>Özellikleri ve paketleri oluşturma
 Visual Studio ilgili SharePoint elemanlara gruplamak için kullanabileceğiniz bir *özelliği*. Örneğin, bir kişi listesi tanımı için bir özellik listesi örneği ve liste tanımını bulunabilir. Tek bir özellik dağıtım amacıyla bu iki öğenin birleştirebilirsiniz. Özellikleri hakkında daha fazla bilgi için bkz: [yapı taşı: Özellikler](http://go.microsoft.com/fwlink/?LinkID=169183).  
  
 Ardından, bir SharePoint çözüm paketi oluşturabilirsiniz (*.wsp*) birden çok özellik paketi için site tanımları, derlemeler ve diğer dosyaları bir biçimde SharePoint tarafından dosyaları dağıtmak için gereken dosyaları depolayan tek bir paket içine Sunucu. Daha fazla bilgi için bkz: [yapı taşı: çözümleri](http://go.microsoft.com/fwlink/?LinkID=169186).  
  
## <a name="feature-and-packaging-tool-support"></a>Özellik ve paketleme aracı desteği
 Hızlı bir şekilde özellikleri ve çözüm paketler daha kolay dağıtım için SharePoint dosyalarınızı düzenlemek için Visual Studio'da SharePoint geliştirme araçlarını kullanabilirsiniz. Özellik ve çözüm paketi yapılandırmak için aşağıdaki araçları kullanabilirsiniz.  
  
-   Özellik Tasarımcısı ve paket tasarımcısını.  
  
-   Paketleme Gezgini'ni, araç penceresi.  
  
-   Çözüm Gezgini.  
  
### <a name="feature-designer-and-package-designer"></a>Özellik Tasarımcısı ve paket Tasarımcısı
 Özellikleri oluşturma kapsamlarını ayarlayın ve özellik Tasarımcısını kullanarak diğer özellikleri bağımlılıklar olarak işaretleyin. Tasarımcı ayrıca her bir özelliğin tanımlayan son XML dosyasını görüntüler. Daha fazla bilgi için bkz: [oluşturma SharePoint özelliklerini](../sharepoint/creating-sharepoint-features.md).  
  
 Özelliği bir özel Web sitesi veya Web sitelerinin gruba ayarlayarak geçerli kendi *kapsam* özellik Tasarımcısı'nda. Tek bir Web sitesi için bir özelliği etkinleştirilmişse, özelliği yalnızca bu belirli bir Web sitede çalışır. Bir özellik için bir site koleksiyonu etkinleştirilmişse, özellik öğelerde tüm site koleksiyonuna uygulayın. Daha fazla bilgi için bkz: [öğe kapsamı](http://go.microsoft.com/fwlink/?LinkID=169189).  
  
 Özellik diğer özellikleri dayalıysa, ayarlayabileceğiniz bir *özelliğini etkinleştirme bağımlılık* bağımlı özellikler, özellik kullanılabilir duruma getirmeden önce işaretlenecek. Özellik etkinleştirme bağımlılık bağımlı özellikler bu kapsamda zaten etkinleştirilmiş olmadığını denetler. Daha fazla bilgi için bkz: [etkinleştirme bağımlılıkları ve kapsam](http://go.microsoft.com/fwlink/?LinkID=169190).  
  
 Paket Tasarımcısı'nda tek çözüm pakete SharePoint öğeleri gruplamak ve Web sunucusu dağıtımı sırasında sıfırlanıp sıfırlanmayacağını yapılandırın. Dağıtım sunucusu türü ayarlamak için kullanın **özellikleri** penceresi. Tasarımcı paket içeriğini açıklayan XML dosyasını da oluşturur. Daha fazla bilgi için bkz: [oluşturma SharePoint çözüm paketlerini](../sharepoint/creating-sharepoint-solution-packages.md).  
  
 Dağıtım sırasında çözüm dosyalarını SharePoint sunucusuna kopyalamak için Internet Information Services (IIS) hizmeti durdurulur. Visual Studio'da paket Tasarımcısını kullanarak, Web sunucusunun yeniden başlatılması gerekmediğini seçebilirsiniz. Çözüm ön uç Web sunucusu veya uygulama sunucusu dağıttıysanız yapılandırmak için kullanın **özellikleri** penceresi. Daha fazla bilgi için bkz: [çözüm öğesi (Çözüm)](http://go.microsoft.com/fwlink/?LinkID=169191).  
  
### <a name="packaging-explorer"></a>Paketleme Gezgini'ni  
 Özellik Tasarımcısı ve paket tasarımcısını tamamlamak için SharePoint dosyalarınızı özellikleri ve paketler halinde gruplamak için paketleme Gezgini'ni kullanabilirsiniz. Ayrıca, paket, özellikler, SharePoint Proje hiyerarşik görünümünü görebilirsiniz öğeleri ve dosyaları. Paketleme Gezgini'ni aşağıdaki görevleri tamamlamak için kullanabileceğiniz bir araç penceresi şöyledir:  
  
-   SharePoint Proje öğeleri ve dosyaları açın.  
  
-   Sürükleyin ve SharePoint Proje öğeleri bir özelliğinden bırakın.  
  
-   Sürükleyin ve SharePoint Proje öğeleri ve özellikleri bir paketten bırakın.  
  
-   Yeni bir özellik için bir paket ekleyin.  
  
-   Bir özellik veya paket Tasarımcısı'nı açın.  
  
-   Özellikleri ve paketleri doğrulayın.  
  
 Visual Studio'da SharePoint geliştirme araçları çözüm paketi doğru biçimlendirildiğinden emin olmak için doğrulama kuralları vardır. Ayrıca, kuralları doğrulayın *.wsp* çözüm dosyasını başarıyla dağıtılabilir ve bir SharePoint sunucusu üzerine etkinleştirildi. Özellikler için XML şeması hakkında daha fazla bilgi için bkz: [özelliği şemaları](http://go.microsoft.com/fwlink/?LinkID=169192).  
  
 SharePoint Proje sistem için özel özellik ve paket doğrulama kuralları ekleyebilirsiniz. Daha fazla bilgi için bkz: [nasıl yapılır: özel özellik ve paket doğrulama kuralları için SharePoint çözümleri oluşturma](../sharepoint/how-to-create-custom-feature-and-package-validation-rules-for-sharepoint-solutions.md).  
  
 Paketleme Gezgini'ni hakkında daha fazla bilgi için bkz: [nasıl yapılır: ekleyip özellikler ve öğeler bir pakete paketleme Gezgini'ni kullanarak](../sharepoint/how-to-add-and-remove-features-and-items-to-a-package-by-using-the-packaging-explorer.md).  
  
### <a name="solution-explorer"></a>Çözüm Gezgini
 Çözüm Gezgini gidin ve SharePoint proje dosyalarını açmak için kullanabilirsiniz. Bağlam menüsü özellikleri, özellik Olay alıcıları eklemek için Çözüm Gezgini'nde kullanın ve kaynaklar özellik. Ayrıca, paket tasarımcıların ve özellik tasarımcıları dağıtımı için paketleri ve özellikleri yapılandırmak için açabilirsiniz.  
  
## <a name="deploy-sharepoint-solutions"></a>SharePoint çözümlerini dağıtma
 Visual Studio'da paket ve Özellikler özelleştirdikten sonra oluşturabileceğiniz bir *.wsp* SharePoint sunucularına dağıtmak için dosya. Hata ayıklama ve test etmek için Visual Studio'yu kullanabilirsiniz. *wsp* yalnızca geliştirme bilgisayarındaki SharePoint sunucusunda. Uzak bir SharePoint server, SharePoint çözümlerini dağıtma hakkında daha fazla bilgi için bkz: [bir çözüm dağıtma](http://go.microsoft.com/fwlink/?LinkID=169194).  
  
 Ayrıca geliştirme bilgisayarındaki dağıtım adımları özelleştirebilirsiniz. Daha fazla bilgi için bkz: [dağıtma, yayımlama ve SharePoint çözüm paketlerini yükseltme](../sharepoint/deploying-publishing-and-upgrading-sharepoint-solution-packages.md).  
  
## <a name="deploy-files-in-sharepoint-solutions"></a>SharePoint çözümlerini dosyalarında dağıtma
 SharePoint çözümünüze bir SharePoint proje öğesi eklediğinizde, genellikle, tüm dosyaları dahil gereklidir. Derlenmiş olabilir dosyalar (kod dosyaları) çözümü çıkış derlemeye oluşturulur. Ancak, aynı zamanda derlenebilir olmayan dosyaları eklemek yaptığınız *.xml*, *.txt*, veya bir SharePoint proje için kaynak dosyaları. Bu dosyalar otomatik olarak çözüm içinde paketlenmiş değil. Paketlenmiş emin olmak için ya da dosyaları eşlenmiş bir klasörde veya bir SharePoint proje öğesi ekleyin.  
  
 Çözüm dağıtıldığında eşlenen klasörler için eklenen dosyalar için SharePoint hive otomatik olarak kopyalanır. Bir SharePoint proje öğesi eklenen dosyaların dağıtılan belirtilen bir konuma **dağıtım konumu** kısmen ayarlanır her dosya için özelliği temel alarak **dağıtım türü** özelliği. Varsayılan olarak, **dağıtım türü** özellik değeri **NoDeployment**, yani dosya çözümüyle dağıtılmaz. Dosyanın pakete dahil etmek özellik için başka bir değer ayarlamanız gerekir.  
  
 Örneğin, eklemek için bir *.xml* dosya bir SharePoint projesine, bu eylemlerden birini gerçekleştirin:  
  
-   Eşlenmiş bir SharePoint "Düzenleri" klasörü projenize ekleyin. Bu oluşturur **Çözüm Gezgini** adlı bir klasör **düzenleri** proje için bir alt klasör sahip. Ekleme *.xml* yeni bir alt dosyasına. Varsayılan olarak, SharePoint dosya sisteminde dosya dağıtılır *... \TEMPLATE\LAYOUTS\\\<klasör adı >*. Eşlenen klasörler ekleme hakkında daha fazla bilgi için bkz: [nasıl yapılır: eşlenmiş klasörler ekleyip](../sharepoint/how-to-add-and-remove-mapped-folders.md).  
  
-   Ekleme *.xml* dosya bir SharePoint proje öğesi klasörüne ve sonra değiştirmek **dağıtım türü** özelliği *.xml* dosya **NoDeployment**  gibi başka bir ayarına **RootFile** veya **ElementFile**. Uygun **dağıtım türü** ayarı, dosya ve proje üzerinde bağlıdır. Hakkında daha fazla bilgi için **dağıtım türü** özellik ayarları bkz [geliştirmek SharePoint çözümlerini](../sharepoint/developing-sharepoint-solutions.md).  
  
 Eklenen dosya çözümü belirli bir proje için geçerli değilse boş bir SharePoint Proje çözümünüze ekleyin ve ek dosya ekleyin. Dosyaları SharePoint için özellikle içerik veritabanını dağıtmak için başka bir alternatif bir modül projeye ekleyin ve sonra dosyaları modülü eklemektir. Daha fazla bilgi için bkz: [çözümde dosyaları eklemeyi modüllerini kullanmanız](../sharepoint/using-modules-to-include-files-in-the-solution.md).  
  
## <a name="see-also"></a>Ayrıca bkz.
 [SharePoint çözümleri geliştirme](../sharepoint/developing-sharepoint-solutions.md)   
 [Derleme ve SharePoint çözümlerini hata ayıklama](../sharepoint/building-and-debugging-sharepoint-solutions.md)  
  
