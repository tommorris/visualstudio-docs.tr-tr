---
title: "Nasıl yapılır: sihirbazları proje şablonlarıyla kullanma | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- project templates [Visual Studio], wizards
- Visual Studio templates, wizards
- wizards [Visual Studio], project templates
- templates [Visual Studio], wizards
- IWizard interface
ms.assetid: 47ee26cf-67b7-4ff1-8a9d-ab11a725405c
caps.latest.revision: "23"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: 8eef98d11f98e3db8216c69dcfacf478c676a837
ms.sourcegitcommit: 5f436413bbb1e8aa18231eb5af210e7595401aa6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/08/2018
---
# <a name="how-to-use-wizards-with-project-templates"></a>Nasıl Yapılır: Sihirbazları Proje Şablonlarıyla Kullanma
Visual Studio sağlar <xref:Microsoft.VisualStudio.TemplateWizard.IWizard> , uygulandığında, arabirim, bir kullanıcı bir şablondan bir proje oluşturduğunda özel kod çalıştırmanızı sağlar.  
  
 Proje şablonu özelleştirme kullanıcı girişi şablonunu özelleştirme, şablona ek dosya ekleyin veya izin verilen herhangi bir işlem bir proje üzerinde toplar özel kullanıcı Arabirimi görüntülemek için kullanılabilir.  
  
 <xref:Microsoft.VisualStudio.TemplateWizard.IWizard> Arabirim yöntemleri, çeşitli zamanlarda çağrılır, proje, bir kullanıcı, hemen sonra başlayan oluşturulurken **Tamam** üzerinde **yeni proje** iletişim kutusu. Her yöntemin arabirimin çağırıldığı noktası açıklamak için adlandırılır. Örneğin, Visual Studio çağırır <xref:Microsoft.VisualStudio.TemplateWizard.IWizard.RunStarted%2A> projesi oluşturmak başladığında hemen kullanıcı girişi toplamak için özel kod yazmanıza için iyi bir konum yapma.  
  
## <a name="creating-a-project-template-project-with-a-vsix-project"></a>VSIX proje ile bir proje şablonu projesi oluşturma  
 Özel bir şablonu proje şablonu proje Visual Studio SDK'sı parçası olan. olarak oluşturmaya başlayın. Bu yordamda bir C# proje şablonu proje kullanacağız, ancak aynı zamanda bir Visual Basic proje şablonu proje yok. Ardından VSIX proje proje şablonu proje içeren çözüme ekleyin.  
  
1.  C# proje şablonu proje oluşturma (Visual Studio'da **Dosya > Yeni > Proje > Visual C# > genişletilebilirlik > C# proje şablonu**). Bu ad **MyProjectTemplate**.  
  
    > [!NOTE]
    >  Visual Studio SDK'yı yüklemeniz istenebilir. Daha fazla bilgi için bkz: [Visual Studio SDK'sını yükleme](../extensibility/installing-the-visual-studio-sdk.md).  
  
2.  Yeni bir VSIX proje ekleyin (**Dosya > Yeni > Proje > Visual C# > genişletilebilirlik > VSIX proje**) proje şablonu proje aynı çözümde (içinde **Çözüm Gezgini**seçin çözüm düğümünü sağ tıklatın ve seçin **Ekle > Yeni proje**). Bu ad **MyProjectWizard.**  
  
3.  VSIX projesini başlangıç projesi olarak ayarlayın. İçinde **Çözüm Gezgini**, VSIX proje düğümüne sağ tıklatın ve seçin seçin **başlangıç projesi olarak ayarla**.  
  
4.  Şablon proje VSIX proje bir varlık ekleyin. İçinde **Çözüm Gezgini**, VSIX proje düğümünde, bulmak **source.extension.vsixmanifest** dosya. Bildirim düzenleyicisinde açmak için çift tıklayın.  
  
5.  Bildirim düzenleyicisinde seçin **varlıklar** pencerenin sol tarafında sekmesinde.  
  
6.  İçinde **varlıklar** sekmesine **yeni**. İçinde **ekleme yeni varlık** select türü alanı penceresi **Microsoft.VisualStudio.ProjectTemplate**. İçinde **kaynak** alan, select **geçerli çözümdeki bir proje ile**. İçinde **proje** alan, select **MyProjectTemplate**. Sonra **Tamam**'a tıklayın.  
  
7.  Çözümü derlemek ve hata ayıklamayı Başlat. Visual Studio ikinci bir örneğini görüntülenir. (Bu işlem birkaç dakika sürebilir.)  
  
8.  Yeni şablonunuz ile yeni bir proje oluşturmak Visual Studio in ikinci örneğini deneyin. (**Dosya > Yeni > Proje > Visual C# > MyProject şablonu**). Yeni Proje adlı bir sınıf ile görünmelidir **Class1**. Özel proje şablonu oluşturdunuz! Artık hata ayıklamayı durdurun.  
  
## <a name="creating-a-custom-template-wizard"></a>Bir özel şablon Sihirbazı oluşturma  
 Bu konu, proje oluşturmadan önce bir Windows formu açılır özel sihirbaz oluşturma gösterilmektedir. Form kullanıcıların kaynak koduna proje oluşturma sırasında eklenen özel parametre değeri eklemesine olanak sağlar.  
  
1.  Bir derlemeyi oluşturmak izin vermek için VSIX projesi ayarlayın.  
  
2.  İçinde **Çözüm Gezgini**, VSIX proje düğümünü seçin. Çözüm Gezgini görmelisiniz **özellikleri** penceresi. Bunu yapmazsanız, seçin **Görünüm > Özellikler penceresini**, veya basın **F4**. Özellikler penceresinde aşağıdaki alanları seçin `true`:  
  
    -   **IncludeAssemblyInVSIXContainer**  
  
    -   **IncludeDebugSymbolsInVSIXContainer**  
  
    -   **IncludeDebugSymbolsInLocalVSIXDeployment**  
  
3.  Derleme bir varlık VSIX projeye ekleyin. Source.extension.vsixmanifest dosyasını açın ve seçin **varlıklar** sekmesi. İçinde **ekleme yeni varlık** penceresinde için **türü** seçin **Microsoft.VisualStudio.Assembly**, için **kaynak** seçin **A Geçerli çözümde proje**ve **proje** seçin **MyProjectWizard**.  
  
4.  VSIX proje aşağıdaki başvurular ekleyin. (İçinde **Çözüm Gezgini**, düğüm Seç altında VSIX proje **başvuruları**, sağ tıklatın ve seçin **Başvuru Ekle**.) İçinde **Başvuru Ekle** iletişim, **Framework** sekmesinde, bulmak **System.Windows Forms** derleme ve seçin. Şimdi seçin **uzantıları** sekmesini Bul **EnvDTE** derleme ve seçin. Ayrıca bulmak **Microsoft.VisualStudio.TemplateWizardInterface** derleme ve seçin. **Tamam**'ı tıklatın.  
  
5.  VSIX Proje Sihirbazı uygulama için bir sınıf ekleyin. (Çözüm Gezgini'nde VSIX proje düğümüne sağ tıklayın ve seçin **Ekle**, ardından **yeni öğe**, ardından **sınıfı**.) Sınıf adını **WizardImplementation**.  
  
6.  Kodla **WizardImplementationClass.cs** aşağıdaki kod ile dosya:  
  
    ```csharp  
    using System;  
    using System.Collections.Generic;  
    using Microsoft.VisualStudio.TemplateWizard;  
    using System.Windows.Forms;  
    using EnvDTE;  
  
    namespace MyProjectWizard  
    {  
        public class WizardImplementation:IWizard  
        {  
            private UserInputForm inputForm;  
            private string customMessage;  
  
            // This method is called before opening any item that   
            // has the OpenInEditor attribute.  
            public void BeforeOpeningFile(ProjectItem projectItem)  
            {  
            }  
  
            public void ProjectFinishedGenerating(Project project)  
            {  
            }  
  
            // This method is only called for item templates,  
            // not for project templates.  
            public void ProjectItemFinishedGenerating(ProjectItem   
                projectItem)  
            {  
            }  
  
            // This method is called after the project is created.  
            public void RunFinished()  
            {  
            }  
  
            public void RunStarted(object automationObject,  
                Dictionary<string, string> replacementsDictionary,  
                WizardRunKind runKind, object[] customParams)  
            {  
                try  
                {  
                    // Display a form to the user. The form collects   
                    // input for the custom message.  
                    inputForm = new UserInputForm();  
                    inputForm.ShowDialog();  
  
                    customMessage = UserInputForm.CustomMessage;  
  
                    // Add custom parameters.  
                    replacementsDictionary.Add("$custommessage$",   
                        customMessage);  
                }  
                catch (Exception ex)  
                {  
                    MessageBox.Show(ex.ToString());  
                }  
            }  
  
            // This method is only called for item templates,  
            // not for project templates.  
            public bool ShouldAddProjectItem(string filePath)  
            {  
                return true;  
            }          
        }  
    }  
    ```  
  
     **UserInputForm** bu başvurulan kodu uygulanan daha sonra.  
  
     `WizardImplementation` Sınıfı içeren her üyesi için yöntemi uygulamaları <xref:Microsoft.VisualStudio.TemplateWizard.IWizard>. Bu örnekte, yalnızca <xref:Microsoft.VisualStudio.TemplateWizard.IWizard.RunStarted%2A> yöntemi bir görevi gerçekleştirir. Diğer tüm yöntemleri hiçbir şey yapma veya dönüş `true`.  
  
     <xref:Microsoft.VisualStudio.TemplateWizard.IWizard.RunStarted%2A> Yöntemi dört parametre kabul eder:  
  
    -   Bir <xref:System.Object> kök dizinine cast parametresi <xref:EnvDTE._DTE> proje özelleştirmenize olanak sağlamak için nesne.  
  
    -   A <xref:System.Collections.Generic.Dictionary%602> şablondaki tüm önceden tanımlanmış parametreleri oluşan bir koleksiyon içeren parametre. Şablon parametreleri hakkında daha fazla bilgi için bkz: [şablon parametreleri](../ide/template-parameters.md).  
  
    -   A <xref:Microsoft.VisualStudio.TemplateWizard.WizardRunKind> ne tür bir şablon kullanılan hakkında bilgi içeren bir parametre.  
  
    -   Bir <xref:System.Object> parametreleri kümesini içeren bir dizi Visual Studio tarafından sihirbaza geçirildi.  
  
     Bu örnek için kullanıcı giriş formundan bir parametre değeri, <xref:System.Collections.Generic.Dictionary%602> parametresi. Her örneğinin `$custommessage$` projesinde parametresi, kullanıcı tarafından girilen metin ile değiştirilecek. Aşağıdaki derlemeler projenize eklemeniz gerekir: **sistem** ve **System.Drawing**.
  
7.  Şimdi oluşturmak **UserInputForm**. İçinde **WizardImplementation.cs** dosya, sonunda aşağıdaki kodu ekleyin **WizardImplementation** sınıfı.  
  
    ```csharp  
    public partial class UserInputForm : Form  
        {  
            private static string customMessage;  
            private TextBox textBox1;  
            private Button button1;  
  
            public UserInputForm()  
            {  
                this.Size = new System.Drawing.Size(155, 265);   
  
                button1 = new Button();  
                button1.Location = new System.Drawing.Point(90, 25);  
                button1.Size = new System.Drawing.Size(50, 25);  
                button1.Click += button1_Click;  
                this.Controls.Add(button1);  
  
                textBox1 = new TextBox();  
                textBox1.Location = new System.Drawing.Point(10, 25);  
                textBox1.Size = new System.Drawing.Size(70, 20);  
                this.Controls.Add(textBox1);  
            }  
            public static string CustomMessage  
            {  
                get  
                {  
                    return customMessage;  
                }  
                set  
                {  
                    customMessage = value;  
                }     
            }  
            private void button1_Click(object sender, EventArgs e)  
            {  
                customMessage = textBox1.Text;  
                this.Close();
            }  
        }  
    ```  
  
     Kullanıcı giriş formu, özel parametre girmek için basit bir form sağlar. Adlı bir metin kutusu formu içeren `textBox1` adlı bir düğmeyi ve `button1`. Düğme tıklatıldığında, metin kutusunun metinden depolanan `customMessage` parametresi.  
  
## <a name="connect-the-wizard-to-the-custom-template"></a>Bağlanma Sihirbazı'nı özel şablonu  
 Özel Sihirbazı'nı kullanmak, özel Proje Şablonu Sihirbazı derlemeyi imzalamak ve yeni bir proje oluşturduğunuzda sihirbaz uygulamasını nerede bulacağını biliyorsanız izin vermek için özel Proje şablonunuza bazı satırlar eklemek gerekir.  
  
1.  Derleme oturum açın. İçinde **Çözüm Gezgini**, VSIX proje, sağ tıklatın ve seçin seçin **proje özelliklerini**.  
  
2.  İçinde **proje özelliklerini** penceresinde, seçin **imzalama** sekmesindeki **imzalama** sekmesi, onay **derlemeyi imzalamak**. İçinde **güçlü ad anahtar dosyası seçin** alan, select  **\<yeni >**. İçinde **güçlü ad anahtarı oluştur** penceresi, **anahtar dosya adını** alanında, yazın **key.snk**. İşaretini **my anahtar dosyasını bir parola ile koruyun** alan.  
  
3.  İçinde **Çözüm Gezgini**, VSIX proje seçin ve Bul **özellikleri** penceresi.  
  
4.  Ayarlama **Kopyala derleme çıktı için çıktı dizini** alanı **doğru**. Bu çözümü yeniden oluşturulduğunda çıkış dizinine kopyalanacağını derleme sağlar. Hala .vsix dosyasında yer alır. Derleme imzalama anahtarının bulmak için bkz: gerekir.  
  
5.  Çözümü yeniden derleyin.  
  
6.  Şimdi key.snk dosya MyProjectWizard proje dizininde bulabilirsiniz (**\<disk konumunuz > \MyProjectTemplate\MyProjectWizard\key.snk**). Key.snk dosyasını kopyalayın.  
  
7.  Çıktı dizinine gidin ve derleme bulunamadı (**\<disk konumunuz > \MyProjectTemplate/MyProjectWizard\bin\Debug\MyProjectWizard.dll**). Burada key.snk dosya yapıştırın. (Bu kesinlikle gerekli değildir, ancak aşağıdaki adımları daha kolay hale getirir.)  
  
8.  Bir komut penceresi açın ve derleme oluşturuldu dizine geçin.  
  
9. Bul **sn.exe** imzalama aracı. Örneğin, bir Windows 10 64-bit işletim sisteminde tipik bir yol şu olacaktır:  
  
     **C:\Program dosyaları (x86) \Microsoft SDKs\Windows\v10.0A\bin\NETFX 4.6.1 araçları**  
  
     Aracı bulamazsa çalıştırmayı deneyin **burada /R.  sn.exe** komut penceresinde. Yolunu not edin.  
  
10. Ortak anahtar key.snk dosyasından ayıklayın. Komut penceresinde yazın  
  
     **\<sn.exe konumunu > \sn.exe -p key.snk outfile.key.**  
  
     Dizin adlarında boşluk varsa tırnak işaretleri sn.exe yolunu çevreleyen unutmayın!  
  
11. Ortak anahtar belirteci ÇıkışDosyası alın:  
  
     **\<sn.exe konumunu > \sn.exe -t outfile.key.**  
  
     Tırnak işaretleri yeniden unutmayın. Bir satırda benzer bir çıktı görmeniz gerekir  
  
     **Ortak anahtar belirteci<token>**  
  
     Bu değeri not edin.  
  
12. Özel sihirbaz referansı proje şablonu .vstemplate dosyasına ekleyin. Çözüm Gezgini'nde, MyProjectTemplate.vstemplate adlı dosyasını bulun ve açın. Sonunda \<TemplateContent > bölümünde, aşağıdaki bölümde ekleyin:  
  
    ```xml  
    <WizardExtension>  
        <Assembly>MyProjectWizard, Version=1.0.0.0, Culture=Neutral, PublicKeyToken=token</Assembly>  
        <FullClassName>MyProjectWizard.WizardImplementation</FullClassName>  
    </WizardExtension>  
    ```  
  
     Burada **MyProjectWizard** derlemenin adıdır ve **belirteci** önceki adımda kopyaladığınız belirteci.  
  
13. Projedeki tüm dosyaları kaydetmek ve yeniden derleyin.  
  
## <a name="adding-the-custom-parameter-to-the-template"></a>Özel parametre şablonuna ekleme  
 Bu örnekte, şablon olarak kullanılan projenin özel sihirbaz kullanıcı giriş formunda belirtilen iletisi görüntüler.  
  
1.  Çözüm Gezgini'nde Git **MyProjectTemplate** proje ve açık **Class1.cs**.  
  
2.  İçinde `Main` yöntemi uygulamanın aşağıdaki kod satırını ekleyin.  
  
    ```  
    Console.WriteLine("$custommessage$");  
    ```  
  
     Parametre `$custommessage$` bir proje şablonu oluşturduğunuzda kullanıcı giriş formunda girilen metin ile değiştirilir.  
  
 Aşağıda, bir şablonu dışarı önce tam kod dosyası verilmiştir.  
  
```csharp  
using System;  
using System.Collections.Generic;  
$if$ ($targetframeworkversion$ >= 3.5)using System.Linq;  
$endif$using System.Text;  
  
namespace $safeprojectname$  
{  
    public class Class1  
    {  
          static void Main(string[] args)  
          {  
               Console.WriteLine("$custommessage$");  
          }  
    }  
}  
```  
  
## <a name="using-the-custom-wizard"></a>Özel sihirbaz kullanma  
 Şimdi, şablonundan bir proje oluşturun ve özel Sihirbazı'nı kullanın.  
  
1.  Çözümü yeniden derleyin ve hata ayıklamayı Başlat. Visual Studio ikinci bir örneğini görüntülenmesi gerekir.  
  
2.  Yeni bir MyProjectTemplate projesi oluşturun. (**Dosya > Yeni > Proje > Visual C# > MyProjectTemplate**)  
  
3.  İçinde **yeni proje** iletişim kutusu, şablonunuzu bulun, bir ad yazın ve tıklatın **Tamam**.  
  
     Sihirbaz kullanıcı giriş formu açılır.  
  
4.  Özel parametre için bir değer yazın ve düğmesini tıklatın.  
  
     Sihirbaz kullanıcı giriş formu kapatır ve bir proje şablonu oluşturulur.  
  
5.  İçinde **Çözüm Gezgini**, kaynak kodu dosyasına sağ tıklatın ve **görünümü kodu**.  
  
     Dikkat `$custommessage$` Sihirbazı kullanıcı giriş formunda girilen metin ile değiştirilmiştir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  

<xref:Microsoft.VisualStudio.TemplateWizard.IWizard>   
[Şablonlarını özelleştirme](../ide/customizing-project-and-item-templates.md)  
[WizardExtension Öğesi (Visual Studio Şablonları)](../extensibility/wizardextension-element-visual-studio-templates.md)  
[Visual Studio şablonları NuGet paketleri](/nuget/visual-studio-extensibility/visual-studio-templates)
