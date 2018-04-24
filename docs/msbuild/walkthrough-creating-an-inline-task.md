---
title: 'İzlenecek yol: satır içi göre oluşturma | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology: msbuild
ms.topic: conceptual
helpviewer_keywords:
- MSBuild, tutorial
- MSBuild, tasks
ms.assetid: 438194cb-668c-41a9-a7e2-c118d14c1ea7
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: b82f9813ce610979cd50a1ced7f510240299a612
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/19/2018
---
# <a name="walkthrough-creating-an-inline-task"></a>İzlenecek Yol: Satır İçi Göre Oluşturma
MSBuild görevleri, uygulayan bir sınıf derleme tarafından genellikle oluşturulan <xref:Microsoft.Build.Framework.ITask> arabirimi. .NET Framework sürüm 4 ile başlayarak, proje dosyasında görevleri satır içi oluşturabilirsiniz. Görev barındırmak için ayrı bir derleme oluşturmak zorunda değildir. Daha fazla bilgi için bkz: [satır içi görevleri](../msbuild/msbuild-inline-tasks.md).  
  
 Bu kılavuz, oluşturmak ve bu satır içi görevleri çalıştırmak gösterilmektedir:  
  
-   Hiçbir giriş veya çıkış parametreleri olan bir görev.  
  
-   Bir giriş parametresi ve hiçbir çıktı parametreleri olan bir görev.  
  
-   İki giriş parametreleri ve MSBuild özelliği döndürür bir çıktı parametresi olan bir görev.  
  
-   İki giriş parametreleri ve MSBuild öğeyi döndürür bir çıktı parametresi olan bir görev.  
  
 Oluşturun ve görevleri çalıştırmak için Visual Studio kullanın ve **Visual Studio komut istemi penceresi**aşağıdaki gibi:  
  
-   Visual Studio kullanarak bir MSBuild proje dosyası oluşturun.  
  
-   Satır içi görevi oluşturmak için Visual Studio Proje dosyasında değiştirin.  
  
-   Kullanım **komut istemi penceresi** projeyi oluşturun ve sonuçlarını inceleyin.  
  
## <a name="creating-and-modifying-an-msbuild-project"></a>Oluşturma ve MSBuild Projesi değiştirme  
 Visual Studio proje sistemi MSBuild'i temel alır. Bu nedenle, Visual Studio kullanarak bir yapı proje dosyası oluşturabilirsiniz. Bu bölümde, bir Visual C# proje dosyası oluşturun. (Visual Basic proje dosyası yerine oluşturabilirsiniz. Bu öğretici bağlamında arasındaki iki proje dosyalarını küçük farktır.)  
  
#### <a name="to-create-and-modify-a-project-file"></a>Oluşturma ve proje dosyasını değiştirme  
  
1.  Visual Studio'da üzerinde **dosya** menüsünde tıklatın **yeni** ve ardından **proje**.  
  
2.  İçinde **yeni proje** Visual C# proje türü ve ardından iletişim kutusunda **Windows Forms uygulaması** şablonu. İçinde **adı** kutusuna `InlineTasks`. Tür a **konumu** bu gibi bir durumda çözüm `D:\`. Emin **çözüm için dizin oluştur** seçildiğinde, **eklemek için kaynak denetimi** işaretli değildir ve **çözüm adı** olan `InlineTasks`.  
  
     Tıklatın **Tamam** proje dosyası oluşturmak için.  
  
3.  İçinde **Çözüm Gezgini**InlineTasks proje düğümüne sağ tıklayın ve ardından **projeyi**.  
  
4.  Proje düğümüne sağ tıklayın ve ardından **Düzenle InlineTasks.csproj**.  
  
     Proje dosyası kod düzenleyicisinde görüntülenir.  
  
## <a name="adding-a-basic-hello-task"></a>Temel Hello görev ekleme  
 Şimdi, proje iletisini görüntüler temel bir görev eklemek "Hello, world!" Ayrıca görev çağırmak için bir varsayılan TestBuild hedefi ekleyin.  
  
#### <a name="to-add-a-basic-hello-task"></a>Bir temel hello görev eklemek için  
  
1.  Kök `Project` düğümü, değişiklik `DefaultTargets` özniteliğini `TestBuild`. Elde edilen `Project` düğüm, bu örnek benzer:  
  
     `<Project ToolsVersion="4.0" DefaultTargets="TestBuild" xmlns="http://schemas.microsoft.com/developer/msbuild/2003">`  
  
2.  Aşağıdaki satır içi görev ekleyin ve proje dosyasına hemen önce hedef `</Project>` etiketi.  
  
    ```xml  
    <UsingTask TaskName="Hello" TaskFactory="CodeTaskFactory" AssemblyFile="$(MSBuildToolsPath)\Microsoft.Build.Tasks.v4.0.dll" >  
      <ParameterGroup />  
      <Task>  
        <Code Type="Fragment" Language="cs">  
          Log.LogMessage("Hello, world!", MessageImportance.High);  
        </Code>  
      </Task>  
    </UsingTask>  
    <Target Name="TestBuild">  
      <Hello />  
    </Target>  
    ```  
  
3.  Proje dosyasını kaydedin.  
  
 Bu kod Hello olarak adlandırılır ve hiçbir parametre başvuruları olan bir satır içi görev oluşturur veya `Using` deyimleri. Merhaba görev yalnızca bir varsayılan günlük kaydı aygıt, genellikle konsol penceresinde hello iletisi görüntüler kod satırı içeriyor.  
  
### <a name="running-the-hello-task"></a>Merhaba görev çalıştırma  
 MSBuild kullanarak çalıştırmak **komut istemi penceresi** Hello görev oluşturmak için ve onu çağırır TestBuild hedef işlemek için.  
  
##### <a name="to-run-the-hello-task"></a>Başlangıç görevi çalıştırmak için  
  
1.  Tıklatın **Başlat**, tıklatın **tüm programlar**ve bulun **Visual Studio Araçları** klasörü ve tıklatın **Visual Studio komut istemi**.  
  
2.  İçinde **komut istemi penceresi**, bu durumda, proje dosyasını içeren klasörü D:\InlineTasks\InlineTasks bulun\\.  
  
3.  Tür **msbuild** olmadan komut anahtarlarını ve ENTER tuşuna BASIN. Varsayılan olarak, bu InlineTasks.csproj dosyasını derler ve varsayılan hedef Hello görev çağırır TestBuild işler.  
  
4.  Çıktıyı inceleyin **komut istemi penceresi**. Şu satırı görmeniz gerekir:  
  
     `Hello, world!`  
  
    > [!NOTE]
    >  Merhaba ileti görmüyorsanız, proje dosyası yeniden kaydetmeyi deneyin ve sonra Hello görevi çalıştırın.  
  
 Kod Düzenleyicisi arasında değişen tarafından ve **komut istemi penceresi**, proje dosyasını değiştirin ve hızlı bir şekilde sonuçları görüntüleyin.  
  
## <a name="defining-the-echo-task"></a>Echo görev tanımlama  
 Bir dize parametresi kabul eder ve dize aygıt günlüğü varsayılan olarak görüntüleyen bir satır içi görevi oluşturun.  
  
#### <a name="to-define-the-echo-task"></a>Echo görev tanımlamak için  
  
1.  Kod Düzenleyicisi'nde Hello görev ve TestBuild hedef aşağıdaki kodu kullanarak değiştirin.  
  
    ```xml  
    <UsingTask TaskName="Echo" TaskFactory="CodeTaskFactory" AssemblyFile="$(MSBuildToolsPath)\Microsoft.Build.Tasks.v4.0.dll" >  
      <ParameterGroup>  
        <Text Required="true" />  
      </ParameterGroup>  
      <Task>  
        <Code Type="Fragment" Language="cs">  
          Log.LogMessage(Text, MessageImportance.High);  
        </Code>  
      </Task>  
    </UsingTask>  
    <Target Name="TestBuild">  
      <Echo Text="Greetings!" />  
    </Target>  
    ```  
  
2.  İçinde **komut istemi penceresi**, türü **msbuild** olmadan komut anahtarlarını ve ENTER tuşuna BASIN. Varsayılan olarak, bu varsayılan hedef Yankı görev çağırır TestBuild işler.  
  
3.  Çıktıyı inceleyin **komut istemi penceresi**. Şu satırı görmeniz gerekir:  
  
     `Greetings!`  
  
 Bu kod, Echo adlandırılmış ve tek gereken giriş parametre metin olan bir satır içi görevi tanımlar. Varsayılan olarak, System.String türünde parametreleridir. TestBuild hedef Yankı görev çalıştırdığında metin parametresinin değeri ayarlanır.  
  
## <a name="defining-the-adder-task"></a>Ekleyici görev tanımlama  
 İki tamsayı parametrelerini ekler ve bunların toplam MSBuild özelliği olarak gösterdiği bir satır içi görevi oluşturun.  
  
#### <a name="to-define-the-adder-task"></a>Ekleyici görev tanımlamak için  
  
1.  Kod Düzenleyicisi'nde, aşağıdaki kodu kullanarak Echo görev ve TestBuild hedef değiştirin.  
  
    ```xml  
    <UsingTask TaskName="Adder" TaskFactory="CodeTaskFactory" AssemblyFile="$(MSBuildToolsPath)\Microsoft.Build.Tasks.v4.0.dll" >  
      <ParameterGroup>  
        <A ParameterType="System.Int32" Required="true" />  
        <B ParameterType="System.Int32" Required="true" />  
        <C ParameterType="System.Int32" Output="true" />  
      </ParameterGroup>  
      <Task>  
        <Code Type="Fragment" Language="cs">  
          C = A + B;  
        </Code>  
      </Task>  
    </UsingTask>    
    <Target Name="TestBuild">  
      <Adder A="4" B="5">  
        <Output PropertyName="Sum" TaskParameter="C" />  
      </Adder>  
      <Message Text="The sum is $(Sum)" Importance="High" />  
    </Target>  
    ```  
  
2.  İçinde **komut istemi penceresi**, türü **msbuild** olmadan komut anahtarlarını ve ENTER tuşuna BASIN. Varsayılan olarak, bu varsayılan hedef Yankı görev çağırır TestBuild işler.  
  
3.  Çıktıyı inceleyin **komut istemi penceresi**. Şu satırı görmeniz gerekir:  
  
     `The sum is 9`  
  
 Bu kod ekleyici adlı bir satır içi görev tanımlar ve iki tamsayı giriş parametreleri, A ve B, gerekli olan ve bir tamsayı çıkış parametresi, c Ekleyici görev iki giriş parametrelerini ekler ve toplam çıkış parametresinde döndürür. Sum MSBuild özelliği olarak gösterilen `Sum`. Girdi parametrelerinin değerlerini TestBuild hedef ekleyici görev çalıştırdığında ayarlanır.  
  
## <a name="defining-the-regx-task"></a>RegX görev tanımlama  
 Bir ürün grubu ve normal bir ifade kabul edip ifadeyle eşleşen dosya içeriği tüm öğeleri listesini döndürür bir satır içi görevi oluşturun.  
  
#### <a name="to-define-the-regx-task"></a>RegX görev tanımlamak için  
  
1.  Kod Düzenleyicisi'nde, aşağıdaki kodu kullanarak ekleyici görev ve TestBuild hedef değiştirin.  
  
    ```xml  
    <UsingTask TaskName="RegX" TaskFactory="CodeTaskFactory" AssemblyFile="$(MSBuildToolsPath)\Microsoft.Build.Tasks.v4.0.dll" >  
      <ParameterGroup>  
        <Expression Required="true" />  
        <Files ParameterType="Microsoft.Build.Framework.ITaskItem[]" Required="true" />  
        <Result ParameterType="Microsoft.Build.Framework.ITaskItem[]" Output="true" />  
      </ParameterGroup>  
      <Task>  
        <Using Namespace="System.Text.RegularExpressions"/>  
        <Code Type="Fragment" Language="cs">  
    <![CDATA[  
          if (Files.Length > 0)  
          {  
            Result = new TaskItem[Files.Length];  
            for (int i = 0; i < Files.Length; i++)  
            {  
              ITaskItem item = Files[i];  
              string path = item.GetMetadata("FullPath");  
              using(StreamReader rdr = File.OpenText(path))  
              {  
                if (Regex.Match(rdr.ReadToEnd(), Expression).Success)  
                {  
                  Result[i] = new TaskItem(item.ItemSpec);  
                }  
              }  
            }  
          }  
    ]]>  
        </Code>  
      </Task>  
    </UsingTask>    
    <Target Name="TestBuild">  
      <RegX Expression="public|protected" Files="@(Compile)">  
        <Output ItemName="MatchedFiles" TaskParameter="Result" />  
      </RegX>  
      <Message Text="Input files: @(Compile)" Importance="High" />  
      <Message Text="Matched files: @(MatchedFiles)" Importance="High" />  
    </Target>  
    ```  
  
2.  İçinde **komut istemi penceresi**, türü **msbuild** olmadan komut anahtarlarını ve ENTER tuşuna BASIN. Varsayılan olarak, bu varsayılan hedef RegX görev çağırır TestBuild işler.  
  
3.  Çıktıyı inceleyin **komut istemi penceresi**. Şu satırları görmeniz gerekir:  
  
     `Input files: Form1.cs;Form1.Designer.cs;Program.cs;Properties\AssemblyInfo.cs;Properties\Resources.Designer.cs;Properties\Settings.Designer.cs`  
  
     `Matched files: Form1.cs;Form1.Designer.cs;Properties\Settings.Designer.cs`  
  
 Bu kod RegX olarak adlandırılır ve şu üç parametreyi olan bir satır içi görev tanımlar:  
  
-   `Expression` eşleştirilecek normal ifade bir değere sahip bir dize gerekli giriş parametresi değil. Bu örnekte, "Genel" veya "korumalı" sözcüklerini ifadeyi eşleştirir.  
  
-   `Files` eşleşme için aranacak dosyaların listesini bir değere sahip gerekli öğe listesi giriş parametresi değil. Bu örnekte, `Files` ayarlanır `Compile` proje kaynak dosyalarını listeler öğesi.  
  
-   `Result` bir değere sahip bir çıktı parametresini normal ifadeyle eşleşen içeriğe sahip dosyaların listesi verilmiştir.  
  
 Giriş parametresi değeri TestBuild hedef RegX görev çalıştırdığında ayarlanır. RegX görev her dosyasını okur ve normal ifade ile eşleşen dosyaları listesini döndürür. Bu liste olarak döndürülür `Result` MSBuild öğesi olarak gösterilen çıktı parametresi `MatchedFiles`.  
  
### <a name="handling-reserved-characters"></a>İşleme ayrılmış karakterlerine  
 MSBuild ayrıştırıcı satır içi görevleri XML olarak işler. Anlamı XML, örneğin, ayrılmış karakterler "\<" ve ">", algılanan ve XML ve .NET kaynak kodu gibi işlenir. Ayrılmış karakter kodu ifadelerinde gibi eklemek için `Files.Length > 0`, yazma `Code` öğesi içeriği aşağıdaki gibi bir CDATA ifadesinde bulunan böylece:  
  
 `<Code Type="Fragment" Language="cs">`  
  
 `<![CDATA[`  
  
 `// Your code goes here.`  
  
 `]]>`  
  
 `</Code>`  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Satır içi görevleri](../msbuild/msbuild-inline-tasks.md)   
 [Görevler](../msbuild/msbuild-tasks.md)   
 [Hedefler](../msbuild/msbuild-targets.md)