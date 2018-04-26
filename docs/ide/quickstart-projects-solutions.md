---
title: Projeler ve çözümler Visual Studio'da giriş
ms.date: 12/11/2017
ms.prod: visual-studio-dev15
ms.technology: vs-ide-general
ms.topic: quickstart
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 3904dfd4a8217a800fb1decf55386142096a2a9a
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/26/2018
---
# <a name="quickstart-projects-and-solutions"></a>Hızlı Başlangıç: Projeler ve çözümler

Bu 10 dakikalık quickstart Visual Studio'da Çözüm ve proje oluşturmak ne anlama geldiğini incelenecektir. Bir proje özelliklerini ve bazı oluşabilir dosyaları bakın. İkinci projesine bir başvuru da oluşturacağız.

Visual Studio henüz yüklemediyseniz, Git [Visual Studio indirmeleri](https://aka.ms/vsdownload?utm_source=mscom&utm_campaign=msdocs) ücretsiz yüklemek için sayfa.

> [!TIP]
> Biz bir çözüm ve proje bu hızlı başlangıç, sıfırdan bir proje kavramı anlamak için eğitim bir alıştırma olarak oluşturma. Visual Studio içinde genel kullanımı, büyük olasılıkla yeni bir proje oluştururken, Visual Studio sunan birçok proje şablonu kullanır.

> [!NOTE]
> Çözümler ve projeler Visual Studio'daki uygulamaları geliştirmek için gerekli değildir. Ayrıca, kodu içeren bir klasörü açın ve kodlama, derleme ve hata ayıklama başlatın. GitHub depo kopyalarsanız, örneğin, bunu Visual Studio projeler ve çözümler içermeyebilir. Daha fazla bilgi için bkz: [projeleri veya çözümler olmadan kod Visual Studio geliştirme](../ide/develop-code-in-visual-studio-without-projects-or-solutions.md).

## <a name="solutions"></a>Çözümleri

Çözümleri bir düzenlemek için Visual Studio tarafından kullanılan kapsayıcılardır veya projeleri ilgili daha fazla. Visual Studio'da bir çözümü açtığınızda, içerdiği tüm projeleri otomatik olarak yükler.

### <a name="create-a-solution"></a>Bir çözümü oluşturma

Bizim araştırması boş çözümünü oluşturarak başlayacağız. Visual Studio tanıyalım sonra büyük olasılıkla boş çözümleri çok sık oluşturduğunuzu bulamaz. Visual Studio'da yeni bir proje oluşturduğunuzda, yoksa bir çözüm zaten açık proje barındırmak için bir çözüm otomatik olarak oluşturur.

1. Visual Studio'yu başlatın.

   Visual Studio açılır ve büyük olasılıkla görürsünüz **başlangıç sayfası** pencerenin Gayrimenkul çoğunu sürüyor.

1. Menü çubuğunda seçin **dosya** > **yeni** > **proje**.

   **Yeni proje** iletişim kutusu açılır.

1. Sol bölmede **diğer proje türleri**, ardından **Visual Studio çözümleri**. Orta bölmede seçin **boş çözüm**. Çözümünüzü "QuickSolution" olarak adlandırın ve ardından **Tamam**.

   ![Boş çözüm şablonu](media/quickstart-projects-new-solution.png)

   **Başlangıç sayfası** kapatır ve çözüm görünür **Çözüm Gezgini** Visual Studio penceresinin sağ tarafında. Büyük olasılıkla kullanacağınız **Çözüm Gezgini** genellikle, projelerinizi içeriğini gidin.

### <a name="add-a-project"></a>Bir proje ekleyin

Artık ilk Projemizin çözüme ekleyelim. Biz, boş bir proje ile başlatın ve ihtiyacımız öğeleri projeye ekleyin.

1. Sağ tıklatın veya bağlam menüsünde **çözüm 'QuickSolution'** içinde **Çözüm Gezgini**, seçin **Ekle** > **yeni proje**.

   **Yeni Proje Ekle** iletişim kutusu açılır.

1. Sol bölmede **Visual C#** ve **Windows Klasik Masaüstü**. Orta bölmede, ardından **boş proje (.NET Framework)**. Projeyi "QuickDate" olarak adlandırın ve ardından **Tamam** düğmesi.

   Çözümde altındaki "QuickDate" adlı bir proje görünür **Çözüm Gezgini**. Şu anda tek dosyalı çağrılan içeren *App.config*.

   > [!NOTE]
   > Görmüyorsanız, **Visual C#** iletişim kutusunun sol bölmesinde yüklemeniz gerekir. **.NET masaüstü geliştirme** iş yükü. Bunu yapmak için kolay bir yol seçmektir **açık Visual Studio yükleyicisi** iletişim kutusunun sol alt köşedeki bağlantıyı. Sonra **Visual Studio yükleyicisi** başlatır, seçin **.NET masaüstü geliştirme** iş yükü ve ardından **Değiştir** düğmesi.

   ![Visual Studio yükleyicisi bağlantıyı aç](media/quickstart-projects-open-installer.png)

## <a name="add-an-item-to-the-project"></a>Projeye bir öğe ekleyin

Boş proje sahibiz&mdash;bir kod dosyası ekleyelim.

1. Sağ tıklatın veya bağlam menüsünde **QuickDate** içinde **Çözüm Gezgini**, seçin **Ekle** > **yeni öğe**.

   **Yeni Öğe Ekle** iletişim kutusu açılır.

1. Genişletme **Visual C# öğeleri**, ardından **kod**. Orta bölmede seçin **sınıfı**. "Takvim" sınıf adını ve ardından **Ekle** düğmesi.

   Adlı bir dosya *Calendar.cs* projeye eklenir. *.Cs* ucunda C# kod dosyaları verilen dosya uzantısıdır. Dosya visual proje hiyerarşisinde görünür **Çözüm Gezgini**, ve içeriğini Düzenleyicisi'nde açılır.

1. Değiştir *Calendar.cs* aşağıdaki kod ile dosya.

   ```csharp
   using System;

   namespace QuickDate
   {
       internal class Calendar
       {
           static void Main(string[] args)
           {
               DateTime now = GetCurrentDate();
               Console.WriteLine($"Today's date is {now}");
               Console.ReadLine();
           }

           internal static DateTime GetCurrentDate()
           {
               return DateTime.Now.Date;
           }
       }
   }
   ```

   Kodun ne yaptığını anlamanıza gerek yoktur, ancak isterseniz, programı çalıştırın ve bugünün tarihini konsol penceresine yazdırır bakın.

## <a name="add-a-second-project"></a>İkinci bir proje ekleyin

Birden çok proje ve genellikle şu projeler başvuru birbirini içeren çözümleri için yaygın bir durumdur. Bir çözümde bazı proje sınıf kitaplıkları, yürütülebilir bazı uygulamalar olabilir ve bazı Birim testi projelerini veya web siteleri olabilir.

Birim testi projesi bizim çözüme ekleyelim. Biz bir ek kod dosyası projeye eklemek zorunda kalmamak için bu süre bir proje şablondan başlayacağız.

1. Sağ tıklatın veya bağlam menüsünde **çözüm 'QuickSolution'** içinde **Çözüm Gezgini**, seçin **Ekle** > **yeni proje**.

   **Yeni Proje Ekle** iletişim kutusu açılır.

1. Sol bölmede **Visual Basic** ve **Test** kategorisi. Orta bölmede seçin **birim testi projesi (.NET Framework)**. Projeyi "QuickTest" olarak adlandırın ve ardından **Tamam** düğmesi.

   İkinci bir proje eklenen **Çözüm Gezgini**ve adlı bir dosya *UnitTest1.vb* Düzenleyicisi'nde açar. *.vb* Visual Basic kodu dosyaları için belirtilen dosya uzantısı.

   ![İki proje ile Çözüm Gezgini](media/quickstart-projects-solution-explorer.png)

## <a name="add-a-project-reference"></a>Proje Başvurusu Ekle

Yeni birim testi projesi bizim yönteminde test etmek için kullanılacak yapacağız **QuickDate** proje, bu nedenle bu projeyi bir başvuru eklemeniz gerekir. Bunun anlamı iki projeler derleme bağımlılıkları oluşturur **QuickDate** önce yerleşik **QuickTest** çözüm ne zaman oluşturulur.

1. Seçin **başvuruları** düğümünde **QuickTest** proje ve sağ tıklatın veya bağlam menüsünü seçin **Başvuru Ekle**.

   ![Başvuru menüsü ekleme](media/quickstart-projects-add-reference.png)

   **Başvuru Yöneticisi** iletişim kutusu açılır.

1. Sol bölmede **projeleri** ve **çözüm**. Orta bölmede, yanındaki onay kutusunu seçin **QuickDate**ve ardından **Tamam** düğmesi.

   Bir başvuru **QuickDate** projesi eklenir.

## <a name="add-test-code"></a>Sınama kodu ekleyin

1. Visual Basic kod dosyasına test kodu şimdi ekleyeceğiz. Değiştir *UnitTest1.vb* aşağıdaki kod ile.

   ```vb
   <TestClass()> Public Class UnitTest1

       <TestMethod()> Public Sub TestGetCurrentDate()
           Assert.AreEqual(DateTime.Now.Date, QuickDate.Calendar.GetCurrentDate())
       End Sub

   End Class
   ```

   "Dalgalı" bazı kodu altında kırmızı görürsünüz. Biz test projesi oluşturarak bu hatayı düzeltmek bir [derlemeyi](/dotnet/csharp/programming-guide/concepts/assemblies-gac/friend-assemblies) için **QuickDate** projesi.

1. Geri **QuickDate** proje, açık *Calendar.cs* zaten açık değilse, dosya ve aşağıdakileri ekleyin deyimiyle ve <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> test projesinin hatayı gidermek için özniteliği.

   ```csharp
   using System.Runtime.CompilerServices;

   [assembly: InternalsVisibleTo("QuickTest")]
   ```

   Kod dosyasını aşağıdaki gibi görünmelidir.

   ![CSharp kodu](media/quickstart-projects-cs-code.png)

## <a name="project-properties"></a>Proje Özellikleri

Dosyasındaki satır içeren C# kod <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> özniteliği başvuran derleme adını **QuickTest** projesi. Proje adı ile aynı derleme adı her zaman olmayabilir. Proje derleme adını bulmak için proje özelliklerini açın.

1. İçinde **Çözüm Gezgini**seçin **QuickTest** projesi. Sağ tıklatın veya bağlam menüsünden seçin **özellikleri**, veya yalnızca basın **Alt**+**Enter**.

   Proje özellik sayfalarını açmak **uygulama** sekmesi. Dikkat derleme adını **QuickTest** projedir gerçekten "QuickTest". Bunu değiştirmek istiyorsanız, burada değişeceğinden budur. Test projesi derlerken, daha sonra sonuçta elde edilen yürütülebilir dosyanın adını gelen değişeceğinden *QuickTest.exe* , seçtiğiniz için.

   ![Proje Özellikleri](media/quickstart-projects-properties.png)

1. Projenin özellik sayfası, diğer sekmeleri bazıları gibi keşfedin **derleme** ve **ayarları**. Bu sekmeleri proje türüne bağlı olarak farklı olacaktır.

## <a name="next-steps"></a>Sonraki adımlar

Birim testi çalıştığını denetlemek istiyorsanız seçin **Test** > **çalıştırmak** > **tüm testleri** menü çubuğundan. Bir pencere olarak adlandırılan **Test Gezgini** açar ve görmeniz gerekir, **TestGetCurrentDate** test geçer.

Bu hızlı başlangıç Tamamlanıyor Tebrikler! Ardından, diğer Quickstarts bazıları için Visual Studio keşfedin veya hakkında daha fazla bilgi edinmek isteyebilirsiniz [projeler ve çözümler oluşturma](../ide/creating-solutions-and-projects.md).

## <a name="see-also"></a>Ayrıca bkz.

- [Hızlı Başlangıç: Visual Studio IDE ilk bakış](../ide/quickstart-ide-orientation.md)
- [Hızlı Başlangıç: Düzenleyicisi ve Visual Studio IDE'yi kişiselleştirme](../ide/quickstart-personalize-the-ide.md)
- [Hızlı Başlangıç: düzenleyicide kodlama](../ide/quickstart-editor.md)
- [Proje ve çözüm özelliklerini yönetme](../ide/managing-project-and-solution-properties.md)
- [Bir projedeki başvuruları yönetme](../ide/managing-references-in-a-project.md)
- [Visual Studio’da projeler veya çözümler olmadan kod geliştirme](../ide/develop-code-in-visual-studio-without-projects-or-solutions.md)
- [Visual Studio IDE genel bakış](../ide/visual-studio-ide.md)