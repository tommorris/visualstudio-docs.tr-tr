---
title: Modelleme çözümünüzün yapısını oluşturma
ms.date: 11/04/2016
ms.topic: conceptual
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.prod: visual-studio-dev15
ms.technology: vs-ide-modeling
ms.openlocfilehash: a18dbf13929163e6f4a0f3d123fe393a188d0830
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/26/2018
---
# <a name="structure-your-modeling-solution"></a>Modelleme çözümünüzün yapısını oluşturma
Bir geliştirme projesinde modelleri etkili bir şekilde kullanmak için ekip üyelerinin projenin farklı parçaları modeller üzerinde aynı anda çalışabilir olması gerekir. Bu konu genel bir Katmanlar karşılık farklı bölümleri uygulamasına bölmek için bir düzen önermektedir katman diyagramı.

 Bir proje üzerinde başlatmak veya hızlı bir şekilde alt proje için seçtiğiniz proje yapısını izleyen bir proje şablonu yararlıdır. Bu konu, oluşturabilir ve bu tür bir şablon kullanmak açıklar.

 Bu konuda, birkaç ekip üyelerinin gerektirecek şekilde büyük ve birkaç takımlar belki de olan bir proje üzerinde çalıştığınız varsayılır. Kodu ve modelleri projenin kaynak denetim sisteminde gibi depolanan [!INCLUDE[esprtfs](../code-quality/includes/esprtfs_md.md)]. En az bazı takım üyeleri modelleri geliştirmek için Visual Studio kullanır ve diğer ekip üyelerinin modelleri diğer Visual Studio sürümlerini kullanarak görüntüleyebilirsiniz.

 Visual Studio hangi sürümlerinin her aracı ve modelleme özellik desteklediğini görmek için bkz: [mimari ve Modelleme Araçları sürüm desteği](../modeling/what-s-new-for-design-in-visual-studio.md#VersionSupport).

## <a name="solution-structure"></a>Çözüm yapısı
 Orta veya büyük bir projede takım yapısı yapısı uygulamanın temel alır. Her takım, bir Visual Studio çözümü kullanır.

#### <a name="to-divide-an-application-into-layers"></a>Bir uygulamayı katmanlara bölmek için

1.  Web uygulaması, hizmet uygulaması veya masaüstü uygulaması gibi uygulamanızın yapısı çözümlerinizi yapısını temel. Ortak mimariler çeşitli içinde ele alınmıştır [Microsoft Uygulama Mimarisi Kılavuzu'nda Uygulama Mimarisi türleri](http://go.microsoft.com/fwlink/?LinkId=196681).

2.  Oluşturma bir [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] Mimari çözüm diyoruz çözümü. Bu çözüm, sistemin genel tasarımını oluşturmak için kullanılır. Modeller, ancak hiçbir kod içerecektir.

     Bir bağımlılık diyagramı bu çözüme ekleyin. Bağımlılık diyagramda, uygulamanız için seçtiğiniz mimariyi çizin. Örneğin, diyagram bu katmanları ve aralarındaki bağımlılıkları gösterebilir: sunu; İş mantığı; ve veri.

4.  Her katman için ayrı bir Visual Studio çözüm mimarisi bağımlılık diyagramda oluşturun.

     Bu çözümler katmanların kodunu geliştirmek için kullanılır.

5.  Katman ve tüm katmanlarda yaygın olan kavramları tasarımları temsil edecek modelleri oluşturun. Modeller, böylece tüm modelleri Mimari çözümünden görülebilir ve ilgili modellerin her katmandan görülebilir düzenleyin.

     Bu aşağıdaki yordamlardan birini kullanarak elde edebilirsiniz. İlk alternatif her katman için ayrı bir modelleme projesi, ve ikinci katmanlar arasında paylaşılan bir tek modelleme projesi oluşturur.

    ###### <a name="to-use-a-separate-modeling-project-for-each-layer"></a>Her katman için ayrı bir modelleme projesi kullanmak için

    1.  Her katman çözümünde bir modelleme projesi oluşturun.

         Bu model, gereksinimleri ve tasarımı bu katmanın açıklayan diyagramları içerecektir. İç içe geçmiş katmanlar gösteren bağımlılık diyagramlar de içerebilir.

         Artık her katman için bir model yanı sıra, uygulama mimarisi için bir modeli vardır. Her model kendi çözümde yer alır. Bu, aynı anda katmanlarda çalışmaya ekip üyelerinin sağlar.

    2.  Mimarisi çözümü için her katman çözümünün modelleme projesine ekleyin. Bunu yapmak için Mimari çözümü açın. Çözüm Gezgini'nde çözüm düğümünü sağ tıklatın, eklenecek gelin ve ardından **mevcut proje**. Bir katmanlı çözümde modelleme projesine (.modelproj) gidin.

         Her model iki çözümlerinde görülebilir: "home", çözümü ve Mimari çözüm.

    3.  Her katman modelleme projesine bir bağımlılık diyagramı ekleyin. Mimari bağımlılık diyagramı bir kopyasını başlatın. Bağımlılık diyagramının bağımlılıkları olmayan parçaları silebilirsiniz.

         Bu katman ayrıntılı yapısını temsil eden bağımlılık diyagramları de ekleyebilirsiniz.

         Bu diyagramları bu katmanda geliştirilen kodu doğrulamak için kullanılır.

    4.  Mimari çözümde, Visual Studio kullanarak gereksinimleri ve tüm katmanların tasarım modelleri düzenleyin.

         Her katman çözümünde modele bakarak, o katman kodunu geliştirin. Modeli güncelleştirmek için aynı bilgisayarı kullanmadan geliştirme yapmak içerik varsa, modeli okuyabilir ve modelleri oluşturulamıyor Visual Studio sürümleri kullanılarak kod geliştirme. Bu sürümleri modelinde kodu da oluşturabilirsiniz.

     Bu yöntem aynı anda katman modellerini düzenleme geliştiriciler tarafından hiçbir girişim neden olabilir güvence altına alır.

     Ancak, modeller ayrı olduğundan, ortak kavramlara başvurmak zordur. Her model üzerinde diğer katmanlara ve mimariye bağımlı öğeleri kopyasını olması gerekir. Her katman bağımlılık diyagramda mimari bağımlılık diyagramı ile eşitlenmiş tutulması gerekir. Bu öğeleri değiştirdiğinizde, bunu başarmak için Araçlar geliştirebilir rağmen eşitleme korumak zordur.

    ###### <a name="to-use-a-separate-package-for-each-layer"></a>Her katman için ayrı bir paket kullanmak için

    1.  Her katman için çözümde Mimarisi Modelleme projesine ekleyin. Çözüm Gezgini'nde, çözüm düğümüne sağ tıklayın, fareyle **Ekle**ve ardından **mevcut proje**. Tek modelleme projesine şimdi her çözümden erişilebilir: Mimari proje ve her katman için geliştirme projesi.

    2.  Paylaşılan modelinde, her katman için bir paket oluşturun: Çözüm Gezgini'nde modelleme projesini seçin. UML Model Gezgini'nde modeli kök düğüme sağ tıklayın, fareyle **Ekle**ve ardından **paket**.

         Her paket gereksinimleri ve karşılık gelen katman tasarımını açıklayan diyagramları içerir.

    3.  Gerekiyorsa, her katman iç yapısı için yerel bağımlılık diyagramları ekleyin.

     Bu yöntem, doğrudan bu katmanların ve bağımlı olduğu ortak mimarisi başvurmak için her bir katmanın tasarım öğeleri sağlar.

     Eşzamanlı iş farklı paketler hakkında bazı çakışmaları neden olabilir ancak bunlar paketleri ayrı dosyalarda saklandığından yönetmek oldukça kolaydır.

## <a name="creating-architecture-templates"></a>Mimari şablonları oluşturma
 Uygulamada, aynı anda tüm Visual Studio çözümleri oluşturmaz ancak Proje ilerledikçe ekleyin. Muhtemelen de aynı çözüm yapısını Gelecek projelerde kullanın.  Yeni çözümleri hızlıca oluşturmanıza yardımcı olması için bir çözüm ya da proje şablonu oluşturabilirsiniz. Böylece dağıtmak ve diğer bilgisayarlara yüklemek için kolay bir Visual Studio Tümleştirme Uzantısı (VSIX) içinde şablon yakalayabilirsiniz.

 Örneğin, sık sık sunu, iş ve veri katmanlarına sahip çözümleri kullanıyorsanız, bu yapıya sahip yeni çözümler oluşturacak bir şablon yapılandırabilirsiniz.

#### <a name="to-create-a-solution-template"></a>Bir çözüm şablonu oluşturmak için

1.  [Şablonu Dışarı Aktarma Sihirbazı'nı yükleyip](http://go.microsoft.com/fwlink/?LinkId=196686), bu yapmış olduğunuz değil.

2.  Gelecekteki projeleri için bir başlangıç noktası olarak kullanmak istediğiniz çözüm yapısını oluşturun.

3.  Üzerinde **dosya** menüsünde tıklatın **VSIX olarak şablonu dışarı aktar**. **VSIX Sihirbazı olarak şablonu dışarı aktar** açar.

4.  Sihirbazdaki yönergeleri şablona dahil, bir ad ve şablon için açıklama girin ve çıkış konumunu belirtmek için istediğiniz projeleri seçin.

> [!NOTE]
>  Bu konudaki malzeme ndan soyutlanır ve Visual Studio mimari araç Visual Studio ALM en değerli uzmanları (MVP), Microsoft Services ve Visual Studio arasında işbirliğini olan Rangers tarafından yazılan Kılavuzu, açıklanır ürün ekibi ve yazarları. [Tam yönergeler paketini karşıdan yüklemek için burayı tıklatın.](http://go.microsoft.com/fwlink/?LinkID=191984)

## <a name="related-materials"></a>İlgili malzemeler
 [Düzenleme ve Modellerinizi yönetme](http://channel9.msdn.com/posts/clinted/UML-with-VS-2010-Part-9-Organizing-and-Managing-Your-Models/) - Clint Edmondson tarafından görüntü.

 [Visual Studio Mimari Kılavuzu Tooling](../modeling/visual-studio-architecture-tooling-guidance.md) -daha fazla takım modellerinde yönetme konusunda yönergeler

## <a name="see-also"></a>Ayrıca Bkz.

- [Geliştirme sürecinizde modelleri kullanma](../modeling/use-models-in-your-development-process.md)
