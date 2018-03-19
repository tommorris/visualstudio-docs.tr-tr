---
title: Using Microsoft.VisualStudio.TestTools.UnitTesting Members in Unit Tests | Microsoft Docs
ms.date: 03/02/2018
ms.technology: vs-ide-test
ms.topic: article
ms.author: gewarren
manager: ghogen
ms.workload:
- multiple
author: gewarren
ms.openlocfilehash: 1ae1f1bd4deb81b92ffc7a38c82164e5824b4d76
ms.sourcegitcommit: 900ed1e299cd5bba56249cef8f5cf3981b10cb1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/19/2018
---
# <a name="use-the-mstest-framework-in-unit-tests"></a>Birim testleri mstest'i framework kullanın

[Mstest'i](<xref:Microsoft.VisualStudio.TestTools.UnitTesting>) framework birim testi Visual Studio'da destekler. Sınıflar ve üyeleri kullanmak <xref:Microsoft.VisualStudio.TestTools.UnitTesting> birim testleri kodlama yaparken ad alanı. Koddan oluşturulan birim testi daraltmayı olduğunda bunları de kullanabilirsiniz.

## <a name="framework-members"></a>Framework üyeleri

Birim testi çerçevesi daha anlaşılır bir genel bakış sağlanmasına yardımcı olmak amacıyla bu bölümde üyelerini düzenler <xref:Microsoft.VisualStudio.TestTools.UnitTesting> ilgili işlevselliği gruplar halinde ad alanı.

> [!NOTE]
> Öznitelik öğeleri, adları "Özniteliği" ile bitmelidir, veya "Özniteliği" olmasın ucunda kullanılabilir. Örneğin, aşağıdaki iki kod örnekleri aynı işlev:
>
> `[TestClass()]`
>
> `[TestClassAttribute()]`

### <a name="members-used-for-data-driven-testing"></a>Veri temelli test etmek için kullanılan üyeler

Veri temelli birim testleri oluşturma için aşağıdaki öğeleri kullanın. Daha fazla bilgi için bkz: [veri-odaklı birim testi oluşturma](../test/how-to-create-a-data-driven-unit-test.md) ve [bir veri kaynağı tanımlamak için bir yapılandırma dosyası kullanmak](../test/walkthrough-using-a-configuration-file-to-define-a-data-source.md).

- <xref:Microsoft.VisualStudio.TestTools.UnitTesting.DataAccessMethod>

- <xref:Microsoft.VisualStudio.TestTools.UnitTesting.DataSourceAttribute>

- <xref:Microsoft.VisualStudio.TestTools.UnitTesting.DataSourceElement>

- <xref:Microsoft.VisualStudio.TestTools.UnitTesting.DataSourceElementCollection>

## <a name="attributes-used-to-establish-a-calling-order"></a>Bir arama sırası kurmak için kullanılan öznitelikleri

Aşağıdaki öznitelikler biri ile donatılmış code öğesi belirttiğiniz şu anda adı verilir. Daha fazla bilgi için bkz: [birim testinin anatomisi](http://msdn.microsoft.com/a03d1ee7-9999-4e7c-85df-7d9073976144).

### <a name="attributes-for-assemblies"></a>Derlemeler için öznitelikler

Derlemenizi kaldırılmadan önce AssemblyInitialize ve AssemblyCleanup derlemenizi yüklendikten sonra sağ ve sağ denir.

- <xref:Microsoft.VisualStudio.TestTools.UnitTesting.AssemblyInitializeAttribute>

- <xref:Microsoft.VisualStudio.TestTools.UnitTesting.AssemblyCleanupAttribute>

### <a name="attributes-for-classes"></a>Sınıfları için öznitelikler

Sınıfınızda kaldırılmadan önce ClassInitialize ve ClassCleanup sınıfınız yüklendikten sonra sağ ve sağ denir.

- <xref:Microsoft.VisualStudio.TestTools.UnitTesting.ClassInitializeAttribute>

- <xref:Microsoft.VisualStudio.TestTools.UnitTesting.ClassCleanupAttribute>

### <a name="attributes-for-test-methods"></a>Test yöntemleri için öznitelikler

- <xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestInitializeAttribute>

- <xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestCleanupAttribute>

## <a name="attributes-used-to-identify-test-classes-and-methods"></a>Test sınıflar ve yöntemler tanımlamak için kullanılan öznitelikleri

Her sınama sınıfı olmalıdır `TestClass` özniteliği ve her test yöntemi olmalıdır `TestMethod` özniteliği. Daha fazla bilgi için bkz: [birim testinin anatomisi](http://msdn.microsoft.com/a03d1ee7-9999-4e7c-85df-7d9073976144).

- <xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestClassAttribute>

- <xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestMethodAttribute>

## <a name="assert-classes-and-related-exceptions"></a>Sınıfları ve ilgili özel durumları onaylama

Birim testleri tarafından onaylar, özel durumlar ve öznitelikleri çeşitli kullanımlarını belirli uygulama davranışını doğrulayabilir. Daha fazla bilgi için bkz: [onay sınıfları kullanma](../test/using-the-assert-classes.md).

- <xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert>

- <xref:Microsoft.VisualStudio.TestTools.UnitTesting.CollectionAssert>

- <xref:Microsoft.VisualStudio.TestTools.UnitTesting.StringAssert>

- <xref:Microsoft.VisualStudio.TestTools.UnitTesting.AssertFailedException>

- <xref:Microsoft.VisualStudio.TestTools.UnitTesting.AssertInconclusiveException>

- <xref:Microsoft.VisualStudio.TestTools.UnitTesting.UnitTestAssertException>

- <xref:Microsoft.VisualStudio.TestTools.UnitTesting.ExpectedExceptionAttribute>

## <a name="the-testcontext-class"></a>Testiyse sınıfı

Aşağıdaki öznitelikler ve atanmış değerleri belirli test yöntemi için Visual Studio özellikleri penceresinde görünür. Bu öznitelikler birim testi kodu erişilebilmesi için düşünülmemiştir. Bunun yerine, birim testi kullanılan veya Çalıştır, IDE, Visual Studio size ya da Visual Studio test altyapısı tarafından yolları etkiler. Örneğin, bu öznitelikler bazıları sütun olarak görünür **Test Yöneticisi** penceresi ve **Test sonuçları** penceresinde testleri gruplandırma ve sıralamayı kullanın ve test sonuçlarını anlamına gelir. Bu tür bir öznitelik <xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestPropertyAttribute>, rasgele meta verileri için birim testleri eklemek için kullanın. Birim testi ile işaretleme tarafından bu test kapsayan bir test geçişi adını depolamak için örneğin, kullanabilirsiniz `[TestProperty("TestPass", "Accessibility")]`. Veya, bir göstergesi olduğu ile test türü depolamak için kullanabilirsiniz `[TestProperty("TestKind", "Localization")]`. Bu öznitelik ve atarsanız, özellik değeri kullanarak oluşturduğunuz özelliği hem de görüntülenir Visual Studio'da **özellikleri** penceresi başlığı altında **Test özel**.

- <xref:Microsoft.VisualStudio.TestTools.UnitTesting.OwnerAttribute>

- <xref:Microsoft.VisualStudio.TestTools.UnitTesting.DeploymentItemAttribute>

- <xref:Microsoft.VisualStudio.TestTools.UnitTesting.DescriptionAttribute>

- <xref:Microsoft.VisualStudio.TestTools.UnitTesting.IgnoreAttribute>

- <xref:Microsoft.VisualStudio.TestTools.UnitTesting.PriorityAttribute>

- <xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestPropertyAttribute>

- <xref:Microsoft.VisualStudio.TestTools.UnitTesting.WorkItemAttribute>

## <a name="test-configuration-classes"></a>Test yapılandırması sınıfları

- <xref:Microsoft.TeamFoundation.TestManagement.Client.ObjectTypes>

- <xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestConfigurationSection>

## <a name="attributes-used-to-generate-reports"></a>Raporlar üretmek için kullanılan öznitelikleri

Bu bölümdeki öznitelikleri, Team Foundation Server takım projesinin proje hiyerarşisinde varlıklara tasarlamanız test yöntemi ilgilidir.

- <xref:Microsoft.VisualStudio.TestTools.UnitTesting.CssIterationAttribute>

- <xref:Microsoft.VisualStudio.TestTools.UnitTesting.CssProjectStructureAttribute>

## <a name="classes-used-with-private-accessors"></a>Özel erişimciler ile kullanılan sınıflar

Birim testi için özel bir yöntem oluşturabilirsiniz. Bu oluşturma bir nesneyi başlatır özel erişimcisi bir sınıf oluşturur <xref:Microsoft.VisualStudio.TestTools.UnitTesting.PrivateObject> sınıfı. <xref:Microsoft.VisualStudio.TestTools.UnitTesting.PrivateObject> Özel erişimcisi işleminin bir parçası yansıma kullanan bir sarmalayıcı sınıfı bir sınıftır. <xref:Microsoft.VisualStudio.TestTools.UnitTesting.PrivateType> Sınıfı benzer, ancak özel örnek yöntemleri çağırmak yerine özel statik yöntemleri çağırmak için kullanılır.

- <xref:Microsoft.VisualStudio.TestTools.UnitTesting.PrivateObject>

- <xref:Microsoft.VisualStudio.TestTools.UnitTesting.PrivateType>

## <a name="see-also"></a>Ayrıca bkz.

- <xref:Microsoft.VisualStudio.TestTools.UnitTesting> başvuru belgeleri
