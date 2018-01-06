---
title: "İzlenecek yol: önce test kullanımından Oluştur özelliği ile geliştirme | Microsoft Docs"
ms.custom: 
ms.date: 10/9/2017
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
dev_langs:
- VB
- CSharp
ms.topic: article
helpviewer_keywords:
- Generate From Usage
- Test-First Development
ms.assetid: 764c17a4-cd95-4c23-bf63-d92d9c5adfb2
caps.latest.revision: "63"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: 1906e55add4dfb4663e3c7da5e84d7538409db17
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="walkthrough-test-first-development-with-the-generate-from-usage-feature"></a>İzlenecek yol: kullanımdan Oluştur özelliği ile önce test geliştirmesi
Bu konuda nasıl kullanılacağı gösterilir [kullanımından Oluştur](../ide/visual-csharp-intellisense.md#generate-from-usage) önce test geliştirmesi destekleyen özelliği.  
  
 *Önce test geliştirme* , ilk ürün belirtimlerini temel birim testleri yazma ve başarılı testleri yapmak için gereken kaynak kodu yazma yazılım tasarımı için bir yaklaşımdır. Visual Studio tanımlanmadan önce ilk önce bunları test çalışmalarınızı başvurduğunuzda yeni türleri ve üyeleri kaynak kodunda oluşturarak önce test geliştirmesi destekler.  
  
 Visual Studio yeni türleri ve iş akışınız için en az kesinti üyeleriyle oluşturur. Geçerli konumunuz kodda ayrılmadan saplamalar türleri, yöntemler, özellikler, alanlar veya oluşturucular oluşturabilirsiniz. Tür oluşturma için seçeneklerini belirtmek için bir iletişim kutusu açtığınızda, iletişim kutusu kapandığında odağı hemen geçerli açık dosyasına döndürür.  
  
 Kullanımdan Oluştur özelliği, Visual Studio ile tümleştirmek test çerçeveleri ile kullanılabilir. Bu konuda, Microsoft birim testi çerçevesi gösterilmiştir.  
  
[!INCLUDE[note_settings_general](../data-tools/includes/note_settings_general_md.md)]  
  
### <a name="to-create-a-windows-class-library-project-and-a-test-project"></a>Bir Windows sınıf kitaplığı proje ve bir Test projesi oluşturmak için  
  
1.  İçinde [!INCLUDE[csprcs](../data-tools/includes/csprcs_md.md)] veya [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)], yeni bir **Windows sınıf kitaplığı** projesi. Bu ad `GFUDemo_VB` veya `GFUDemo_CS`kullanmakta olduğunuz dili bağlı olarak.  
  
2.  İçinde **Çözüm Gezgini**, üst çözüm simgesine sağ tıklayın, seçin **Ekle**ve ardından **yeni proje**. Sol bölmesinde **yeni proje** iletişim kutusunda, seçin **Test**.  
  
3.  Orta bölmede seçin **birim testi projesi** ve UnitTestProject1 varsayılan adını kabul edin. Görünür zaman iletişim kutusu aşağıda gösterilmiştir [!INCLUDE[csprcs](../data-tools/includes/csprcs_md.md)]. İçinde [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)], iletişim kutusu benzer.  
  
     ![Yeni Test projesi iletişim kutusu](../ide/media/newproject_test.png "NewProject_Test")  
  
4.  Seçin **Tamam** kapatmak için **yeni proje** iletişim kutusu.  

### <a name="to-add-a-reference-to-the-class-library-project"></a>Sınıf kitaplığı projesine bir başvuru eklemek için

1.  İçinde **Çözüm Gezgini**, projeyi biriminiz altında test, sağ **başvuruları** girişi ve seçin **Başvuru Ekle**.

2.  İçinde **başvuru Yöneticisi** iletişim kutusunda **projeleri** ve ardından sınıf kitaplığı projesini seçin.

3.  Seçin **Tamam** kapatmak için **başvuru Yöneticisi** iletişim kutusu.  
    
4.  Çözümünüzü kaydedin. Şimdi testleri yazmaya başlamak hazırsınız.  
  
### <a name="to-generate-a-new-class-from-a-unit-test"></a>Yeni bir sınıf bir birim testi oluşturmak için  
  
1.  Oluşturduğunuz test projesinin UnitTest1 adlı bir dosya içeriyor. Bu dosyasına çift tıklayarak **Çözüm Gezgini** Kod düzenleyicisinde açın. Bir test sınıfı ve test yöntemi oluşturulmuş.  
  
2.  Sınıf bildirimi bulun `UnitTest1` ve ona yeniden adlandırın `AutomobileTest`.  
  
 > [!NOTE]
 >  IntelliSense şimdi IntelliSense deyimi tamamlama için iki seçenek sunar: *tamamlanma modu* ve *öneri modu*. Öneri Modu tanımlanmadan önce sınıflar ve üyeleri kullanılan durumlar için kullanın. IntelliSense penceresi açıkken basabilirsiniz **Ctrl + Alt + boşluk** tamamlama modu ve öneri modu arasında geçiş yapmak için. Bkz: [kullanarak IntelliSense](../ide/using-intellisense.md) daha fazla bilgi için. Öneri Modu yardımcı olacak yazarken `Automobile` sonraki adımda.  
  
3.  Bulun `TestMethod1()` yöntemi ve ona yeniden adlandırın `DefaultAutomobileIsInitializedCorrectly()`. Bu yöntem içinde adlı bir sınıf yeni bir örneğini oluşturmak `Automobile`aşağıdaki ekran görüntülerinde gösterildiği gibi. Dalgalı alt çizgiyle görünür, derleme zamanı hatası gösterir ve [hızlı Eylemler](../ide/quick-actions.md) ampul, sol kenar boşluğunda (C# yalnızca) veya doğrudan dalgalı altında üzerine getirirseniz görüntülenir.  
  
     ![Visual Basic'de hızlı Eylemler](../ide/media/genclass_underlinevb.png "GenClass_UnderlineVB")  

     ![Hızlı Eylemler C &#35; ] (../ide/media/genclass_underline.png "GenClass_Underline")  
  
4.  Seçin veya hızlı Eylemler ampul tıklatın. Bildiren bir hata iletisi görürsünüz türü `Automobile` tanımlı değil. Ayrıca, bazı çözümleriyle sunulur.  
  
5. Tıklatın **yeni türünü oluştur...**  açmak için **oluşturmak türü** iletişim kutusu. Bu iletişim kutusu türü farklı bir projedeki oluşturma dahil seçenekleri sunar.  

6. İçinde **proje** tıklatın **GFUDemo\_VB** veya **GFUDemo_CS** sınıf kitaplığı proje testi yerine dosya eklemek için Visual Studio istemek için Proje. Henüz seçili değilse seçin **oluştur yeni dosya** ve adlandırın **Automobile.cs** veya **Automobile.vb**.  
  
     ![Yeni türü iletişim kutusu üretmek](../ide/media/genotherdialog.png "GenOtherDialog")  
  
6.  Tıklatın **Tamam** iletişim kutusunu kapatmak ve yeni dosya oluşturun.  
  
7.  İçinde **Çözüm Gezgini**, doğrulamak için GFUDemo_VB veya GFUDemo_CS proje düğümünde yeni Automobile.vb arayın veya Automobile.cs dosyası vardır. Kod Düzenleyicisi'nde odağı hala kullanımda `AutomobileTest.DefaultAutomobileIsInitializedCorrectly`, kesinti en az testinizle yazmaya devam sağlar.  
  
### <a name="to-generate-a-property-stub"></a>Bir özellik saplama oluşturmak için  
Ürün belirtimi belirten varsayın `Automobile` sınıfına sahip adlı iki ortak özellikler `Model` ve `TopSpeed`. Bu özellikleri varsayılan değerlerle başlatılmalıdır `"Not specified"` ve `-1` varsayılan oluşturucu tarafından. Aşağıdaki birim testi varsayılan oluşturucu doğru varsayılan değerlerine özellikleri oluşturduğunu doğrular.  
  
1. Aşağıdaki kod satırını ekleyin `DefaultAutomobileIsInitializedCorrectly` test yöntemi.  
  
     [!code-csharp[VbTDDWalkthrough#1](../ide/codesnippet/CSharp/walkthrough-test-first-support-with-the-generate-from-usage-feature_1.cs)]
     [!code-vb[VbTDDWalkthrough#1](../ide/codesnippet/VisualBasic/walkthrough-test-first-support-with-the-generate-from-usage-feature_1.vb)]  
  
2. Kod üzerinde iki tanımlanmamış özellikler başvurduğundan `Automobile`, altında dalgalı alt çizgiyle görünür `Model` ve `TopSpeed`. Üzerine gelerek `Model` ve hızlı Eylemler ampul seçin ve ardından **özelliği 'Automobile.Model' oluşturmak**.  

3. Bir özellik saplama için oluşturmak `TopSpeed` aynı şekilde özelliği.  
  
     İçinde `Automobile` sınıfı, yeni özelliklerin türleri doğru bağlamdan sonuçlandı.  
  
### <a name="to-generate-a-stub-for-a-new-constructor"></a>Yeni bir oluşturucu için bir saplama oluşturmak için  
Başlatmak için Oluşturucusu saplama oluşturacak bir test yöntemi oluşturacağız artık `Model` ve `TopSpeed` özellikleri. Daha sonra sınama işlemini tamamlamak için daha fazla kod ekleyeceksiniz.  

1. Aşağıdaki ek test yöntemine ekleyin, `AutomobileTest` sınıfı.  
  
     [!code-csharp[VbTDDWalkthrough#2](../ide/codesnippet/CSharp/walkthrough-test-first-support-with-the-generate-from-usage-feature_2.cs)]
     [!code-vb[VbTDDWalkthrough#2](../ide/codesnippet/VisualBasic/walkthrough-test-first-support-with-the-generate-from-usage-feature_2.vb)]  
  
2.  Hızlı Eylemler ampul altında kırmızı dalgalı tıklayın ve ardından **'Otomobil' Generate Oluşturucuda**.  

     İçinde `Automobile` sınıf dosya, yeni Oluşturucusu Oluşturucusu çağrısında kullanılan yerel değişkenleri adlarını incelenmesi dikkat edin, aynı adı taşıyan özellikler bulundu `Automobile` sınıfı ve Oluşturucusu gövdesinde sağlanan kodu bağımsız değişkeni değerlerini depolamak `Model` ve `TopSpeed` özellikleri.
  

3.  Yeni Oluşturucusu oluşturduktan sonra varsayılan bir oluşturucu çağrısı altında dalgalı alt çizgiyle görünür `DefaultAutomobileIsInitializedCorrectly`. Hata iletisi `Automobile` sınıfına sahip sıfır bağımsız değişken alan oluşturucu yok. Parametrelere sahip olmayan bir açık varsayılan bir oluşturucu oluşturmak için hızlı Eylemler ampul'ı tıklatın ve ardından **'Otomobil' Generate Oluşturucuda**.  
  
### <a name="to-generate-a-stub-for-a-method"></a>Bir yöntem için bir saplama oluşturmak için  
Belirtimi belirten varsayın yeni bir `Automobile` çalışan bir duruma durumunda yerleştirme kendi `Model` ve `TopSpeed` özellikler varsayılan değerleri dışında bir şey için ayarlanır.  

1. Aşağıdaki satırları ekleyin `AutomobileWithModelNameCanStart` yöntemi.
  
     [!code-csharp[VbTDDWalkthrough#3](../ide/codesnippet/CSharp/walkthrough-test-first-support-with-the-generate-from-usage-feature_3.cs)]
     [!code-vb[VbTDDWalkthrough#3](../ide/codesnippet/VisualBasic/walkthrough-test-first-support-with-the-generate-from-usage-feature_3.vb)]  
  
2.  Hızlı Eylemler ampul tıklatın `myAuto.Start` yöntemini çağırın ve ardından **üretme yöntemi 'Automobile.Start'**.  
  
3.  Hızlı Eylemler ampul tıklatın `IsRunning` özelliği ve ardından **özelliği 'Automobile.IsRunning' oluşturmak**.  

     `Automobile` Sınıfı şimdi adlı bir yöntem içerir `Start()` ve adlı bir özellik `IsRunning`.  
  
### <a name="to-run-the-tests"></a>Testleri çalıştırmak için  
  
1.  Üzerinde **Test** menüsünde seçin **çalıştırmak**, **tüm testleri**.  

     **Çalıştırmak**, **tüm testleri** komutu geçerli çözüm için yazılmış olan herhangi bir test çerçeve tüm testleri çalıştırır. Bu durumda, iki testleri vardır ve her ikisi de beklendiği gibi başarısız olur. `DefaultAutomobileIsInitializedCorrectly` Test başarısız olduğundan `Assert.IsTrue` koşul döndürür `False`. `AutomobileWithModelNameCanStart` Test başarısız olduğundan `Start` yönteminde `Automobile` sınıfı bir özel durum oluşturur.  
  
     **Test sonuçlarını** penceresinde aşağıdaki çizimde gösterilmiştir.  
  
     ![Test sonuçları başarısız](../ide/media/testsfailed.png "TestsFailed")  
  
2.  İçinde **Test sonuçları** penceresi, her test konuma gitmek için her test sonucu satırda çift tıklatın.  
  
### <a name="to-implement-the-source-code"></a>Kaynak kodu uygulamak için  
  
1.  Aşağıdaki kodu için varsayılan oluşturucu şekilde ekleme `Model`, `TopSpeed` ve `IsRunning` özellikleri tüm başlatılır doğru varsayılan değerlerine `"Not specified"`, `-1`, ve `False` (veya `false` C# ').  
  
     [!code-csharp[VbTDDWalkthrough#5](../ide/codesnippet/CSharp/walkthrough-test-first-support-with-the-generate-from-usage-feature_5.cs)]
     [!code-vb[VbTDDWalkthrough#5](../ide/codesnippet/VisualBasic/walkthrough-test-first-support-with-the-generate-from-usage-feature_5.vb)]  
  
2.  Zaman `Start` yöntemi çağrıldığında, ayarlamanız gerekir `IsRunning` tek ise true bayrak `Model` veya `TopSpeed` özellikleri varsayılan değerlerine dışında bir şey için ayarlanır. Kaldırma `NotImplementedException` yönteminden gövde ve aşağıdaki kodu ekleyin.  
  
     [!code-csharp[VbTDDWalkthrough#6](../ide/codesnippet/CSharp/walkthrough-test-first-support-with-the-generate-from-usage-feature_6.cs)]
     [!code-vb[VbTDDWalkthrough#6](../ide/codesnippet/VisualBasic/walkthrough-test-first-support-with-the-generate-from-usage-feature_6.vb)]  
  
### <a name="to-run-the-tests-again"></a>Testleri yeniden çalıştırmak için  
  
- Üzerinde **Test** menüsündeki **çalıştırmak**ve ardından **tüm testleri**.  

     Bu süre testleri geçirin. **Test sonuçlarını** penceresinde aşağıdaki çizimde gösterilmiştir.  
  
     ![Test sonuçları geçirilen](../ide/media/testspassed.png "TestsPassed")
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Kullanımdan oluştur](../ide/visual-csharp-intellisense.md#generate-from-usage)   
 [Kod yazma](../ide/writing-code-in-the-code-and-text-editor.md)   
 [IntelliSense kullanma](../ide/using-intellisense.md)   
 [Kodunuza Birim Testi Uygulama](../test/unit-test-your-code.md)  
 [Hızlı Eylemler](../ide/quick-actions.md)  