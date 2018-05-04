---
title: 'İzlenecek yol: Kullanımdan Oluştur özelliği ile önce Test geliştirmesi'
ms.date: 10/09/2017
ms.prod: visual-studio-dev15
ms.technology: vs-ide-general
dev_langs:
- VB
- CSharp
ms.topic: conceptual
helpviewer_keywords:
- Generate From Usage
- Test-First Development
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 624e66486dfd2c4e75b12cfdce1d3758ab37de60
ms.sourcegitcommit: a8e01952be5a539104e2c599e9b8945322118055
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
---
# <a name="walkthrough-test-first-development-with-the-generate-from-usage-feature"></a>İzlenecek yol: Kullanımdan Oluştur özelliği ile önce Test geliştirmesi

Bu konuda nasıl kullanılacağı gösterilir [kullanımından Oluştur](../ide/visual-csharp-intellisense.md#generate-from-usage) önce test geliştirmesi destekleyen özelliği.

 *Önce test geliştirme* , ilk ürün belirtimlerini temel birim testleri yazma ve başarılı testleri yapmak için gereken kaynak kodu yazma yazılım tasarımı için bir yaklaşımdır. Visual Studio tanımlanmadan önce ilk önce bunları test çalışmalarınızı başvurduğunuzda yeni türleri ve üyeleri kaynak kodunda oluşturarak önce test geliştirmesi destekler.

 Visual Studio yeni türleri ve iş akışınız için en az kesinti üyeleriyle oluşturur. Geçerli konumunuz kodda ayrılmadan saplamalar türleri, yöntemler, özellikler, alanlar veya oluşturucular oluşturabilirsiniz. Tür oluşturma için seçeneklerini belirtmek için bir iletişim kutusu açtığınızda, iletişim kutusu kapandığında odağı hemen geçerli açık dosyasına döndürür.

 **Kullanımından Oluştur** özelliği, Visual Studio ile tümleştirmek test çerçevelerini birlikte kullanılabilir. Bu konuda, Microsoft birim testi çerçevesi gösterilmiştir.

[!INCLUDE[note_settings_general](../data-tools/includes/note_settings_general_md.md)]

### <a name="create-a-windows-class-library-project-and-a-test-project"></a>Bir Windows sınıf kitaplığı proje ve bir Test projesi oluşturma

1.  İçinde [!INCLUDE[csprcs](../data-tools/includes/csprcs_md.md)] veya [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)], yeni bir **Windows sınıf kitaplığı** projesi. Bu ad `GFUDemo_VB` veya `GFUDemo_CS`kullanmakta olduğunuz dili bağlı olarak.

2.  İçinde **Çözüm Gezgini**, üst çözüm simgesine sağ tıklayın, seçin **Ekle**ve ardından **yeni proje**. Sol bölmesinde **yeni proje** iletişim kutusunda, seçin **Test**.

3.  Orta bölmede seçin **birim testi projesi** ve varsayılan adı kabul `UnitTestProject1`. Görünür zaman iletişim kutusu aşağıda gösterilmiştir [!INCLUDE[csprcs](../data-tools/includes/csprcs_md.md)]. İçinde [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)], iletişim kutusu benzer.

     ![Yeni Test projesi iletişim kutusu](../ide/media/newproject_test.png "NewProject_Test")

4.  Seçin **Tamam** kapatmak için **yeni proje** iletişim kutusu.

### <a name="add-a-reference-to-the-class-library-project"></a>Sınıf kitaplığı projesine bir başvuru ekleyin

1.  İçinde **Çözüm Gezgini**, projeyi biriminiz altında test, sağ **başvuruları** girişi ve seçin **Başvuru Ekle**.

2.  İçinde **başvuru Yöneticisi** iletişim kutusunda **projeleri** ve ardından sınıf kitaplığı projesini seçin.

3.  Seçin **Tamam** kapatmak için **başvuru Yöneticisi** iletişim kutusu.

4.  Çözümünüzü kaydedin. Şimdi testleri yazmaya başlamak hazırsınız.

### <a name="generate-a-new-class-from-a-unit-test"></a>Yeni bir sınıf bir birim testi oluşturma

1.  Test projesi adlı bir dosyayı içeren *UnitTest1*. Bu dosyasına çift tıklayarak **Çözüm Gezgini** Kod düzenleyicisinde açın. Bir test sınıfı ve test yöntemi oluşturulmuş.

2.  Sınıf bildirimi bulun `UnitTest1` ve ona yeniden adlandırın `AutomobileTest`.

 > [!NOTE]
 >  IntelliSense şimdi IntelliSense deyimi tamamlama için iki seçenek sunar: *tamamlanma modu* ve *öneri modu*. Öneri Modu tanımlanmadan önce sınıflar ve üyeleri kullanılan durumlar için kullanın. Zaman bir **IntelliSense** penceresini açın, basabilirsiniz **Ctrl**+**Alt**+**alanı** arasında geçiş yapmak için Tamamlanma modu ve öneri modu. Bkz: [kullanım IntelliSense](../ide/using-intellisense.md) daha fazla bilgi için. Öneri Modu yardımcı olacak yazarken `Automobile` sonraki adımda.

3.  Bulun `TestMethod1()` yöntemi ve ona yeniden adlandırın `DefaultAutomobileIsInitializedCorrectly()`. Bu yöntem içinde adlı bir sınıf yeni bir örneğini oluşturmak `Automobile`aşağıdaki ekran görüntülerinde gösterildiği gibi. Dalgalı alt çizgiyle görünür, derleme zamanı hatası gösterir ve [hızlı Eylemler](../ide/quick-actions.md) ampul, sol kenar boşluğunda (C# yalnızca) veya doğrudan dalgalı altında üzerine getirirseniz görüntülenir.

     ![Visual Basic'de hızlı Eylemler](../ide/media/genclass_underlinevb.png "GenClass_UnderlineVB")

     ![C'de hızlı Eylemler&#35;](../ide/media/genclass_underline.png "GenClass_Underline")

4.  Seçin veya tıklatın **hızlı Eylemler** ampul. Bildiren bir hata iletisi görürsünüz türü `Automobile` tanımlı değil. Ayrıca, bazı çözümleriyle sunulur.

5. Tıklatın **yeni türü** açmak için **oluşturmak türü** iletişim kutusu. Bu iletişim kutusu türü farklı bir projedeki oluşturma dahil seçenekleri sunar.

6. İçinde **proje** tıklatın **GFUDemo\_VB** veya **GFUDemo_CS** sınıf kitaplığı proje testi yerine dosya eklemek için Visual Studio istemek için Proje. Henüz seçili değilse seçin **oluştur yeni dosya** ve adlandırın *Automobile.cs* veya *Automobile.vb*.

     ![Yeni türü iletişim kutusu üretmek](../ide/media/genotherdialog.png "GenOtherDialog")

6.  Tıklatın **Tamam** iletişim kutusunu kapatmak ve yeni dosya oluşturun.

7.  İçinde **Çözüm Gezgini**, altında Ara **GFUDemo_VB** veya **GFUDemo_CS** doğrulamak için proje düğümüne yeni *Automobile.vb* veya  *Automobile.cs* dosyasıdır vardır. Kod Düzenleyicisi'nde odağı hala kullanımda `AutomobileTest.DefaultAutomobileIsInitializedCorrectly`, kesinti en az testinizle yazmaya devam sağlar.

### <a name="generate-a-property-stub"></a>Bir özellik saplama oluştur
Ürün belirtimi belirten varsayın `Automobile` sınıfına sahip adlı iki ortak özellikler `Model` ve `TopSpeed`. Bu özellikleri varsayılan değerlerle başlatılmalıdır `"Not specified"` ve `-1` varsayılan oluşturucu tarafından. Aşağıdaki birim testi varsayılan oluşturucu doğru varsayılan değerlerine özellikleri oluşturduğunu doğrular.

1. Aşağıdaki kod satırını ekleyin `DefaultAutomobileIsInitializedCorrectly` test yöntemi.

     [!code-csharp[VbTDDWalkthrough#1](../ide/codesnippet/CSharp/walkthrough-test-first-support-with-the-generate-from-usage-feature_1.cs)]
     [!code-vb[VbTDDWalkthrough#1](../ide/codesnippet/VisualBasic/walkthrough-test-first-support-with-the-generate-from-usage-feature_1.vb)]

2. Kod üzerinde iki tanımlanmamış özellikler başvurduğundan `Automobile`, altında dalgalı alt çizgiyle görünür `Model` ve `TopSpeed`. Üzerine gelerek `Model` ve **hızlı Eylemler** ampul sonra seçin **özelliği 'Automobile.Model' oluşturmak**.

3. Bir özellik saplama için oluşturmak `TopSpeed` aynı şekilde özelliği.

     İçinde `Automobile` sınıfı, yeni özelliklerin türleri doğru bağlamdan sonuçlandı.

### <a name="generate-a-stub-for-a-new-constructor"></a>Yeni bir oluşturucu için bir saplama oluştur
Başlatmak için Oluşturucusu saplama oluşturacak bir test yöntemi oluşturacağız artık `Model` ve `TopSpeed` özellikleri. Daha sonra sınama işlemini tamamlamak için daha fazla kod ekleyeceksiniz.

1. Aşağıdaki ek test yöntemine ekleyin, `AutomobileTest` sınıfı.

     [!code-csharp[VbTDDWalkthrough#2](../ide/codesnippet/CSharp/walkthrough-test-first-support-with-the-generate-from-usage-feature_2.cs)]
     [!code-vb[VbTDDWalkthrough#2](../ide/codesnippet/VisualBasic/walkthrough-test-first-support-with-the-generate-from-usage-feature_2.vb)]

2.  Tıklatın **hızlı Eylemler** ampul kırmızı dalgalı altında ve ardından **'Otomobil' Generate Oluşturucuda**.

     İçinde `Automobile` sınıf dosya, yeni Oluşturucusu Oluşturucusu çağrısında kullanılan yerel değişkenleri adlarını incelenmesi dikkat edin, aynı adı taşıyan özellikler bulundu `Automobile` sınıfı ve Oluşturucusu gövdesinde sağlanan kodu bağımsız değişkeni değerlerini depolamak `Model` ve `TopSpeed` özellikleri.


3.  Yeni Oluşturucusu oluşturduktan sonra varsayılan bir oluşturucu çağrısı altında dalgalı alt çizgiyle görünür `DefaultAutomobileIsInitializedCorrectly`. Hata iletisi `Automobile` sınıfına sahip sıfır bağımsız değişken alan oluşturucu yok. Parametrelere sahip olmayan bir açık varsayılan bir oluşturucu oluşturmak için tıklatın **hızlı Eylemler** ampul ve ardından **'Otomobil' Generate Oluşturucuda**.

### <a name="generate-a-stub-for-a-method"></a>Bir yöntem için bir saplama oluştur
Belirtimi belirten varsayın yeni bir `Automobile` içine koyabilirsiniz bir `IsRunning` varsa durum kendi `Model` ve `TopSpeed` özellikler varsayılan değerleri dışında bir şey için ayarlanır.

1. Aşağıdaki satırları ekleyin `AutomobileWithModelNameCanStart` yöntemi.

     [!code-csharp[VbTDDWalkthrough#3](../ide/codesnippet/CSharp/walkthrough-test-first-support-with-the-generate-from-usage-feature_3.cs)]
     [!code-vb[VbTDDWalkthrough#3](../ide/codesnippet/VisualBasic/walkthrough-test-first-support-with-the-generate-from-usage-feature_3.vb)]

2.  Tıklatın **hızlı Eylemler** ampul için `myAuto.Start` yöntemini çağırın ve ardından **üretme yöntemi 'Automobile.Start'**.

3.  Tıklatın **hızlı Eylemler** ampul için `IsRunning` özelliği ve ardından **özelliği 'Automobile.IsRunning' oluşturmak**.

     `Automobile` Sınıfı şimdi adlı bir yöntem içerir `Start()` ve adlı bir özellik `IsRunning`.

### <a name="run-the-tests"></a>Testleri çalıştırma

1.  Üzerinde **Test** menüsünde seçin **çalıştırmak** > **tüm testleri**.

     **Çalıştırmak** > **tüm testleri** komutu geçerli çözüm için yazılmış olan herhangi bir test çerçeve tüm testleri çalıştırır. Bu durumda, iki testleri vardır ve her ikisi de beklendiği gibi başarısız olur. `DefaultAutomobileIsInitializedCorrectly` Test başarısız olduğundan `Assert.IsTrue` koşul döndürür `False`. `AutomobileWithModelNameCanStart` Test başarısız olduğundan `Start` yönteminde `Automobile` sınıfı bir özel durum oluşturur.

     **Test sonuçlarını** penceresinde aşağıdaki çizimde gösterilmiştir.

     ![Test sonuçları başarısız](../ide/media/testsfailed.png "TestsFailed")

2.  İçinde **Test sonuçları** penceresi, her test konuma gitmek için her test sonucu satırda çift tıklatın.

### <a name="implement-the-source-code"></a>Uygulama kaynak kodu

1.  Aşağıdaki kodu için varsayılan oluşturucu şekilde ekleme `Model`, `TopSpeed` ve `IsRunning` özellikleri tüm başlatılır doğru varsayılan değerlerine `"Not specified"`, `-1`, ve `False` (veya `false` C# ').

     [!code-csharp[VbTDDWalkthrough#5](../ide/codesnippet/CSharp/walkthrough-test-first-support-with-the-generate-from-usage-feature_5.cs)]
     [!code-vb[VbTDDWalkthrough#5](../ide/codesnippet/VisualBasic/walkthrough-test-first-support-with-the-generate-from-usage-feature_5.vb)]

2.  Zaman `Start` yöntemi çağrıldığında, ayarlamanız gerekir `IsRunning` tek ise true bayrak `Model` veya `TopSpeed` özellikleri varsayılan değerlerine dışında bir şey için ayarlanır. Kaldırma `NotImplementedException` yönteminden gövde ve aşağıdaki kodu ekleyin.

     [!code-csharp[VbTDDWalkthrough#6](../ide/codesnippet/CSharp/walkthrough-test-first-support-with-the-generate-from-usage-feature_6.cs)]
     [!code-vb[VbTDDWalkthrough#6](../ide/codesnippet/VisualBasic/walkthrough-test-first-support-with-the-generate-from-usage-feature_6.vb)]

### <a name="run-the-tests-again"></a>Testleri yeniden çalıştırın

- Üzerinde **Test** menüsündeki **çalıştırmak**ve ardından **tüm testleri**.

     Bu süre testleri geçirin. **Test sonuçlarını** penceresinde aşağıdaki çizimde gösterilmiştir.

     ![Test sonuçları geçirilen](../ide/media/testspassed.png "TestsPassed")

## <a name="see-also"></a>Ayrıca bkz.

- [Kullanımdan oluştur](../ide/visual-csharp-intellisense.md#generate-from-usage)
- [Kod yazma](../ide/writing-code-in-the-code-and-text-editor.md)
- [IntelliSense kullanma](../ide/using-intellisense.md)
- [Birim testi kodunuz](../test/unit-test-your-code.md)
- [Hızlı Eylemler](../ide/quick-actions.md)