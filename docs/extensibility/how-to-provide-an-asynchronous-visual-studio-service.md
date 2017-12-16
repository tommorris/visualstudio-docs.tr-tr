---
title: "Nasıl yapılır: bir zaman uyumsuz Visual Studio hizmet sağlayan | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 0448274c-d3d2-4e12-9d11-8aca78a1f3f5
caps.latest.revision: "10"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 1bcf34f730411589624075bde4ace0b5457e07a7
ms.sourcegitcommit: f36eb7f989efbdbed0d0a087afea8ffe27d8ca15
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/14/2017
---
# <a name="how-to-provide-an-asynchronous-visual-studio-service"></a>Nasıl yapılır: bir zaman uyumsuz Visual Studio hizmet sağlayın
Bir hizmeti kullanıcı Arabirimi iş parçacığı engellenmeden edinmek istiyorsanız, zaman uyumsuz bir hizmet oluşturmak ve arka plan iş parçacığında paketi gerekir. Bu amaçla kullanabileceğiniz bir <xref:Microsoft.VisualStudio.Shell.AsyncPackage> yerine <xref:Microsoft.VisualStudio.Shell.Package>ve zaman uyumsuz paketin özel zaman uyumsuz yöntemleri ile Hizmet Ekle  
  
 Visual Studio Hizmetleri zaman uyumlu sağlama hakkında daha fazla bilgi için bkz: [nasıl yapılır: bir hizmet sağlamak](../extensibility/how-to-provide-a-service.md).  
  
## <a name="implementing-an-asynchronous-service"></a>Zaman uyumsuz bir hizmet uygulama  
  
1.  VSIX proje oluşturma (**Dosya > Yeni > Proje > Visual C# > Extensiblity > VSIX proje**). Proje adı **TestAsync**.  
  
2.  Bir VSPackage projeye ekleyin. Proje düğümünde seçin **Çözüm Gezgini** tıklatıp **Ekle > Yeni Öğe > Visual C# öğeleri > genişletilebilirlik > Visual Studio Paketi**. Bu dosya adı **TestAsyncPackage.cs**.  
  
3.  TestAsyncPackage.cs içinde paket yerine AsyncPackage devralmak için paket değiştirin:  
  
    ```csharp  
    public sealed class TestAsyncPackage : AsyncPackage  
    ```  
  
4.  Bir hizmet uygulamak için üç tür oluşturmanız gerekir:  
  
    -   Hizmet açıklayan bir arabirim. Bu arabirimleri çoğunu boş, diğer bir deyişle, yöntemlerin hiçbiri sahiptirler.  
  
    -   Hizmet arabirimi açıklayan bir arabirim. Bu arabirim, uygulanacak yöntemleri içerir.  
  
    -   Hem hizmet hem de hizmet arabirimi uygulayan bir sınıf.  
  
5.  Aşağıdaki örnek çok basit bir uygulama üç tür gösterir. Hizmet sınıf hizmet sağlayıcısı ayarlamanız gerekir. Bu örnekte, yalnızca hizmet paketi kod dosyasına ekleyeceğiz.  
  
6.  Aşağıdaki using deyimlerini paket dosyası:  
  
    ```csharp  
    using System.Threading;  
    using System.Threading.Tasks;  
    using System.Runtime.CompilerServices;  
    using System.IO;  
    ```  
  
7.  Zaman uyumsuz hizmet uygulaması aşağıda verilmiştir. Zaman uyumlu bir hizmet sağlayıcısı yerine zaman uyumsuz hizmet sağlayıcısı oluşturucuda ayarlamak gerektiğini unutmayın:  
  
    ```  
    public class TextWriterService : STextWriterService, ITextWriterService  
    {  
        private Microsoft.VisualStudio.Shell.IAsyncServiceProvider serviceProvider;  
        public TextWriterService(Microsoft.VisualStudio.Shell.IAsyncServiceProvider provider)  
        {  
            serviceProvider = provider;  
        }  
        public async System.Threading.Tasks.Task WriteLineAsync(string path, string line)  
        {  
            StreamWriter writer = new StreamWriter(path);  
            await writer.WriteLineAsync(line);  
            writer.Close();  
        }  
        public TaskAwaiter GetAwaiter()  
        {  
            return new TaskAwaiter();  
        }  
    }  
    public interface STextWriterService  
    {  
    }  
    public interface ITextWriterService   
    {  
        System.Threading.Tasks.Task WriteLineAsync(string path, string line);  
        TaskAwaiter GetAwaiter();  
    }  
    ```  
  
## <a name="registering-a-service"></a>Bir hizmeti kaydetme  
 Bir hizmeti kaydetmek için ekleme <xref:Microsoft.VisualStudio.Shell.ProvideServiceAttribute> hizmeti sağlayan pakete. Zaman uyumlu bir hizmeti kaydetme gelen iki farklar vardır:  
  
-   Autoloading varsa paket eklemelisiniz <xref:Microsoft.VisualStudio.Shell.PackageAutoLoadFlags> öznitelik BackgroundLoad değerine. Autoloading VSPackages hakkında daha fazla bilgi için bkz: [yüklenirken VSPackages](../extensibility/loading-vspackages.md).  
  
-   Eklemelisiniz **AllowsBackgroundLoading = true** alanı <xref:Microsoft.VisualStudio.Shell.PackageRegistrationAttribute>. PackageRegistrationAttribute hakkında daha fazla bilgi için bkz: [kaydetme ve kaydını kaldırma VSPackages](../extensibility/registering-and-unregistering-vspackages.md).  
  
 Bir zaman uyumsuz hizmet kaydı ile bir AsyncPackage bir örneği burada verilmiştir::  
  
```csharp  
[ProvideService((typeof(STextWriterService)), IsAsyncQueryable = true)]  
[ProvideAutoLoad(UIContextGuids80.SolutionExists, PackageAutoLoadFlags.BackgroundLoad)]  
[PackageRegistration(UseManagedResourcesOnly = true, AllowsBackgroundLoading = true)]   
[Guid(TestAsyncPackage.PackageGuidString)]  
public sealed class TestAsyncPackage : AsyncPackage  
{. . . }  
```  
  
## <a name="adding-a-service"></a>Bir hizmet ekleme  
  
1.  TestAsyncPackage.cs içinde kaldırmak `Initialize()` yöntemi ve geçersiz kılma `InitializeAsync()` yöntemi. Hizmet ekleyin ve hizmetleri oluşturmak için bir geri çağırma yöntemi ekleyin. Bir hizmet ekleme zaman uyumsuz Başlatıcı bir örneği burada verilmiştir:  
  
    ```  
    protected override async System.Threading.Tasks.Task InitializeAsync(CancellationToken cancellationToken, IProgress<ServiceProgressData> progress)  
    {  
        this.AddService(typeof(STextWriterService), CreateService);  
  
        await base.InitializeAsync(cancellationToken, progress);  
    }  
  
    ```  
  
2.  Microsoft.VisualStudio.Shell.Interop.14.0.DesignTime.dll bir başvuru ekleyin.  
  
3.  Geri çağırma yöntemi oluşturur ve hizmet döndüren zaman uyumsuz bir yöntem uygular.  
  
    ```csharp  
    public async System.Threading.Tasks.Task<object> CreateService(IAsyncServiceContainer container, CancellationToken cancellationToken, Type serviceType)  
    {  
        STextWriterService service = null;  
        await System.Threading.Tasks.Task.Run(() => {  
                    service = new TextWriterService(this);  
             });  
  
        return service;  
    }  
  
    ```  
  
## <a name="using-a-service"></a>Bir hizmeti kullanma  
 Şimdi hizmetin ve yöntemlerini kullanın.  
  
1.  Bu Başlatıcı göstereceğiz, ancak herhangi bir yere hizmet kullanmak istediğiniz hizmet elde edebilirsiniz.  
  
    ```csharp  
    protected override async System.Threading.Tasks.Task InitializeAsync(CancellationToken cancellationToken, IProgress<ServiceProgressData> progress)  
    {  
        this.AddService(typeof(STextWriterService), CreateService);  
  
        ITextWriterService textService = await this.GetServiceAsync(typeof(STextWriterService)) as ITextWriterService;  
  
        await writer.WriteLineAsync(<userpath>), "this is a test");  
  
        await base.InitializeAsync(cancellationToken, progress);  
    }  
  
    ```  
  
     Değiştirmeyi unutmayın  *\<userpath >* bir dosya adı ve makinenizde mantıklı yolu!  
  
2.  Derleme ve kodu çalıştırın. Visual Studio'nun deneysel örneği göründüğünde, bir çözüm açın. Bu autoload için AsyncPackage neden olur. Başlatıcı çalıştırıldığında, belirtilen konumda bir dosya bulmanız gerekir.  
  
## <a name="using-an-asynchronous-service-in-a-command-handler"></a>Zaman uyumsuz bir hizmet bir komut işleyici kullanma  
 Zaman uyumsuz bir hizmet bir menü komutunu kullanmak nasıl bir örneği burada verilmiştir. Diğer zaman uyumsuz olmayan yöntemlerle hizmeti kullanmak için burada gösterilen yordamı kullanabilirsiniz.  
  
1.  Menü komutu projenize ekleyin. (İçinde **Çözüm Gezgini**, proje düğümüne sağ tıklatın ve seçin seçin **Ekle / yeni öğe / genişletilebilirlik / özel komut**.) Komut dosyasının adı **TestAsyncCommand.cs.**  
  
2.  Özel komut şablonunu yeniden ekler `Initialize()` komutu başlatmak için TestAsyncPackage.cs dosyasına yöntemi. Önce Initialize() yöntemini başlatır komut satırı kopyalayın. Aşağıdaki gibi görünmelidir:  
  
    ```  
    TestAsyncCommand.Initialize(this);  
    ```  
  
     Bu satır taşıma `InitializeAsync()` AsyncPackageForService.cs dosyasındaki yöntemi. Zaman uyumsuz bir başlatma olduğundan komutunu kullanarak başlatılmadan önce ana iş parçacığına geçmelidir <xref:Microsoft.VisualStudio.Threading.JoinableTaskFactory.SwitchToMainThreadAsync%2A>. Bunu şu şekilde görünmelidir:  
  
    ```csharp  
  
    protected override async System.Threading.Tasks.Task InitializeAsync(CancellationToken cancellationToken, IProgress<ServiceProgressData> progress)  
    {  
        await ThreadHelper.JoinableTaskFactory.SwitchToMainThreadAsync();  
        TestAsyncCommand.Initialize(this);    
  
        this.AddService(typeof(STextWriterService), CreateService);  
  
        ITextWriterService textService =   
           await this.GetServiceAsync(typeof(STextWriterService)) as ITextWriterService;  
  
        await writer.WriteLineAsync((<userpath>, "this is a test");  
  
        await base.InitializeAsync(cancellationToken, progress);  
    }  
  
    ```  
  
3.  Silme `Initialize()` yöntemi.  
  
4.  TestAsyncCommand.cs dosyasını bulun `MenuItemCallback()` yöntemi. Yönteminin gövdesi silin.  
  
5.  Kullanarak bir ekleme deyimi:  
  
    ```  
    using System.IO;  
    ```  
  
6.  Adlı zaman uyumsuz bir yöntem eklemek `GetAsyncService()`, hangi hizmet alır ve kendi yöntemleri kullanır:  
  
    ```csharp  
    private async System.Threading.Tasks.Task GetAsyncService()  
    {  
        ITextWriterService textService =   
           this.ServiceProvider.GetService(typeof(STextWriterService))  
              as ITextWriterService;  
        // don't forget to change <userpath> to a local path  
        await writer.WriteLineAsync((<userpath>),"this is a test");  
       }  
  
    ```  
  
7.  Bu yöntemi çağırın `MenuItemCallback()` yöntemi:  
  
    ```  
    private void MenuItemCallback(object sender, EventArgs e)  
    {  
        GetAsyncService();  
    }  
  
    ```  
  
8.  Çözümü derlemek ve hata ayıklamayı Başlat. Visual Studio'nun deneysel örneği göründüğünde, Git **Araçları** menü ve Ara **çağırma TestAsyncCommand** menü öğesi. Tıklattığınızda, TextWriterService, belirtilen dosyaya yazar. (Komut çağırma Ayrıca paket yüklemek neden olduğundan, bir çözüm açmanız gerekmez.)  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Hizmetleri Kullanma ve Sağlama](../extensibility/using-and-providing-services.md)