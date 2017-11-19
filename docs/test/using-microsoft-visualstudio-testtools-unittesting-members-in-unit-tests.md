---
title: "Birim testlerinde Microsoft.VisualStudio.TestTools.UnitTesting üyelerini kullanma | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-devops-test
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 0fa335fd-e442-448f-913f-25a19df90a93
caps.latest.revision: "6"
ms.author: douge
manager: douge
ms.openlocfilehash: 1a723104cdd350dcc2c5fac80eef4e98b178df4c
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
---
# <a name="using-microsoftvisualstudiotesttoolsunittesting-members-in-unit-tests"></a>Birim Testlerinde Microsoft.VisualStudio.TestTools.UnitTesting Üyelerini Kullanma
Birim testi çerçevesi birim içinde testi destekleyen [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]. Sınıflar ve üyeleri Microsoft.VisualStudio.TestPlatform.UnitTestFramework kullanmak > birim testleri kodlama yaparken ad alanı. Birim sıfırdan test veya test ettiğiniz koddan oluşturulan birim testi iyileştirme yazılmış olduğunda bunları kullanabilirsiniz.  
  
## <a name="groups-of-elements"></a>Öğelerin grupları  
 Birim testi çerçevesi daha anlaşılır bir genel bakış sağlanmasına yardımcı olmak amacıyla bu bölümde UnitTesting ad alanı öğeleri ilgili işlevselliği gruplar halinde düzenler.  
  
> [!NOTE]
>  Öznitelik öğeleri, adları dize özniteliği sonuçlandırmak, veya öznitelik dize olmasın kullanılabilir. Örneğin, aşağıdaki iki kod örnekleri aynı işlev:  
>   
>  `[TestClass()]`  
>   
>  `[TestClassAttribute()]`  
  
### <a name="elements-used-for-data-driven-testing"></a>Veri temelli test etmek için kullanılan öğeleri  
 Veri temelli birim testleri oluşturma için aşağıdaki öğeleri kullanın. Daha fazla bilgi için bkz: [nasıl yapılır: bir veri-odaklı birim testi oluşturma](../test/how-to-create-a-data-driven-unit-test.md) ve [izlenecek yol: bir veri kaynağı tanımlamak için bir yapılandırma dosyası kullanarak](../test/walkthrough-using-a-configuration-file-to-define-a-data-source.md).  
  
-   Microsoft.VisualStudio.TestPlatform.UnitTestFramework.DataAccessMethod  
  
-   Microsoft.VisualStudio.TestPlatform.UnitTestFramework.DataSourceAttribute 
  
-   Microsoft.VisualStudio.TestPlatform.UnitTestFramework.DataSourceElement  
  
-   Microsoft.VisualStudio.TestPlatform.UnitTestFramework.DataSourceElementCollection  
  
## <a name="attributes-used-to-establish-a-calling-order"></a>Bir arama sırası kurmak için kullanılan öznitelikleri  
 Aşağıdaki öznitelikler biri ile donatılmış code öğesi belirttiğiniz şu anda adı verilir. Daha fazla bilgi için bkz: [birim testinin anatomisi](http://msdn.microsoft.com/en-us/a03d1ee7-9999-4e7c-85df-7d9073976144).  
  
### <a name="for-assemblies"></a>Derlemeler için  
 Derlemenizi kaldırılmadan önce AssemblyInitialize ve AssemblyCleanup derlemenizi yüklendikten sonra sağ ve sağ denir.  
  
-   Microsoft.VisualStudio.TestPlatform.UnitTestFramework.AssemblyInitializeAttribute  
  
-   Microsoft.VisualStudio.TestPlatform.UnitTestFramework.AssemblyCleanupAttribute  
  
### <a name="for-classes"></a>İçin sınıflar  
 Sınıfınızda kaldırılmadan önce ClassInitialize ve ClassCleanup sınıfınız yüklendikten sonra sağ ve sağ denir.  
  
-   Microsoft.VisualStudio.TestPlatform.UnitTestFramework.ClassInitializeAttribute  
  
-   Microsoft.VisualStudio.TestPlatform.UnitTestFramework.ClassCleanupAttribute  
  
### <a name="for-test-methods"></a>Test yöntemleri  
  
-   Microsoft.VisualStudio.TestPlatform.UnitTestFramework.TestInitializeAttribute  
  
-   Microsoft.VisualStudio.TestPlatform.UnitTestFramework.TestCleanupAttribute  
  
## <a name="attributes-used-to-identify-test-classes-and-methods"></a>Test sınıflar ve yöntemler tanımlamak için kullanılan öznitelikleri  
 Her test sınıfı TestClass özniteliğe sahip olması gerekir ve her test yöntemi TestMethod özniteliğe sahip olması gerekir. Daha fazla bilgi için bkz: [birim testinin anatomisi](http://msdn.microsoft.com/en-us/a03d1ee7-9999-4e7c-85df-7d9073976144).  
  
-   Microsoft.VisualStudio.TestPlatform.UnitTestFramework.TestClassAttribute  
  
-   Microsoft.VisualStudio.TestPlatform.UnitTestFramework.TestMethodAttribute  
  
## <a name="assert-classes-and-related-exceptions"></a>Sınıfları ve ilgili özel durumları onaylama  
 Birim testleri tarafından Assert deyimleri, özel durumlar ve öznitelikleri çeşitli kullanımlarını belirli uygulama davranışını doğrulayabilir. Daha fazla bilgi için bkz: [onay sınıfları kullanma](../test/using-the-assert-classes.md).  
  
-   Microsoft.VisualStudio.TestPlatform.UnitTestFramework.Assert 
  
-   Microsoft.VisualStudio.TestPlatform.UnitTestFramework.CollectionAssert  
  
-   Microsoft.VisualStudio.TestPlatform.UnitTestFramework.StringAssert  
  
-   Microsoft.VisualStudio.TestPlatform.UnitTestFramework.AssertFailedException  
  
-   Microsoft.VisualStudio.TestPlatform.UnitTestFramework.AssertInconclusiveException  
  
-   Microsoft.VisualStudio.TestPlatform.UnitTestFramework.UnitTestAssertException  
  
-   Microsoft.VisualStudio.TestPlatform.UnitTestFramework.ExpectedExceptionAttribute  
  
## <a name="the-testcontext-class"></a>Testiyse sınıfı  
 Aşağıdaki öznitelikler ve atanmış değer görünür [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] belirli test yöntemi için Özellikler penceresini. Bu öznitelikler birim testi kodu erişilebilmesi için düşünülmemiştir. Bunun yerine, bunlar çalıştırın, IDE aracılığıyla sizin tarafınızdan veya birim testi kullanılan yolu etkileyen [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)], ya da [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] test altyapısı. Örneğin, bazı bu özniteliklerin Test Yöneticisi'ni ve testleri gruplandırma ve sıralamayı kullanın ve test sonuçlarını anlamına gelir Test Sonuçları penceresinde sütun olarak görünür. Bu tür bir öznitelik için birim testleri rastgele meta verileri eklemek için kullandığınız TestPropertyAttribute ' dir. Birim testi ile işaretleme tarafından bu test kapsayan bir test geçişi adını depolamak için örneğin, kullanabilirsiniz `[TestProperty("TestPass", "Accessibility")]`. Veya bir göstergesi olduğu test türü depolamak için kullanabilirsiniz: `[TestProperty("TestKind", "Localization")]`. Bu öznitelik ve atadığınız özellik değerini kullanarak oluşturduğunuz özelliği, hem de görüntülenen [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] Özellikler penceresi başlığı altında **Test özel**.  
  
-   Microsoft.VisualStudio.TestPlatform.UnitTestFramework.OwnerAttribute  
  
-   Microsoft.VisualStudio.TestPlatform.UnitTestFramework.DeploymentItemAttribute  
  
-   Microsoft.VisualStudio.TestPlatform.UnitTestFramework.DescriptionAttribute  
  
-   Microsoft.VisualStudio.TestPlatform.UnitTestFramework.HostTypeAttribute  
  
-   Microsoft.VisualStudio.TestPlatform.UnitTestFramework.IgnoreAttribute  
  
-   Microsoft.VisualStudio.TestPlatform.UnitTestFramework.PriorityAttribute  
  
-   Microsoft.VisualStudio.TestPlatform.UnitTestFramework.TestPropertyAttribute  
  
-   Microsoft.VisualStudio.TestPlatform.UnitTestFramework.WorkItemAttribute  
  
## <a name="test-configuration-classes"></a>Test yapılandırması sınıfları  
  
-   Microsoft.TeamFoundation.TestManagement.Client.ObjectTypes >  
  
-   Microsoft.VisualStudio.TestPlatform.UnitTestFramework.TestConfigurationSection  
  
## <a name="attributes-used-for-generating-reports"></a>Rapor oluşturma için kullanılan öznitelikleri  
 Bu bölümdeki öznitelikleri bunlar proje hiyerarşisini varlıklarla tasarlamanız test yöntemi ile ilgili bir [!INCLUDE[esprtfs](../code-quality/includes/esprtfs_md.md)] takım projesi.  
  
-   Microsoft.VisualStudio.TestPlatform.UnitTestFramework.CssIterationAttribute  
  
-   Microsoft.VisualStudio.TestPlatform.UnitTestFramework.CssProjectStructureAttribute  
  
## <a name="classes-used-with-private-accessors"></a>Özel erişimciler ile kullanılan sınıflar  
 Bölümünde açıklandığı gibi [kullanarak bir özel erişimcisi oluşturmak için duyurun](http://msdn.microsoft.com/en-us/2056c6a7-6672-42a7-8f53-fead33c56deb), birim testi için özel bir yöntem oluşturabilirsiniz. Bu oluşturma PrivateObject sınıfın bir nesnesi başlatır özel erişimcisi bir sınıf oluşturur. PrivateObject sınıfı özel erişimcisi işleminin bir parçası yansıma kullanan bir sarmalayıcı sınıftır. PrivateType sınıfı benzer, ancak özel örnek yöntemleri çağırmak yerine özel statik yöntemleri çağırmak için kullanılır.  
  
-   Microsoft.VisualStudio.TestPlatform.UnitTestFramework.PrivateObject  
  
-   Microsoft.VisualStudio.TestPlatform.UnitTestFramework.PrivateType  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 Microsoft.VisualStudio.TestPlatform.UnitTestFramework
