---
title: 'Nasıl yapılır: bir zaman uyumsuz Visual Studio hizmet sağlayan | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.topic: conceptual
ms.assetid: 0448274c-d3d2-4e12-9d11-8aca78a1f3f5
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 8741779cf96cb970f3ebc4907443b85ced5b80c0
ms.sourcegitcommit: fe5a72bc4c291500f0bf4d6e0778107eb8c905f5
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/07/2018
ms.locfileid: "33705079"
---
# <a name="how-to-provide-an-asynchronous-visual-studio-service"></a>Nasıl yapılır: bir zaman uyumsuz Visual Studio hizmet sağlayın
Bir hizmeti kullanıcı Arabirimi iş parçacığı engellenmeden edinmek istiyorsanız, zaman uyumsuz bir hizmet oluşturmak ve arka plan iş parçacığında paketi gerekir. Bu amaçla kullanabileceğiniz bir <xref:Microsoft.VisualStudio.Shell.AsyncPackage> yerine <xref:Microsoft.VisualStudio.Shell.Package>ve zaman uyumsuz paketin özel zaman uyumsuz yöntemleri ile hizmetini ekleyin.
  
 Visual Studio Hizmetleri zaman uyumlu sağlama hakkında daha fazla bilgi için bkz: [nasıl yapılır: bir hizmet sağlamak](../extensibility/how-to-provide-a-service.md).  
  
## <a name="implementing-an-asynchronous-service"></a>Zaman uyumsuz bir hizmet uygulama  
  
1.  VSIX proje oluşturma (**Dosya > Yeni > Proje > Visual C# > Extensiblity > VSIX proje**). Proje adı **TestAsync**.  
  
2.  Bir VSPackage projeye ekleyin. Proje düğümünde seçin **Çözüm Gezgini** tıklatıp **Ekle > Yeni Öğe > Visual C# öğeleri > genişletilebilirlik > Visual Studio Paketi**. Bu dosya adı **TestAsyncPackage.cs**.  
  
3.  TestAsyncPackage.cs içinde paket yerine AsyncPackage devralmak için paket değiştirin:  
  
    ```csharp  
    public sealed class TestAsyncPackage : AsyncPackage  
    ```  
  
4.  Bir hizmet uygulamak için üç tür oluşturmanız gerekir:  
  
    -   Hizmeti tanıtan bir arabirim. Bu arabirimleri çoğunu boş, yalnızca hizmet sorgulama için kullanıldıkları gibi diğer bir deyişle, yöntemlerin hiçbiri sahiptirler.
  
    -   Hizmet arabirimi açıklayan bir arabirim. Bu arabirim, uygulanacak yöntemleri içerir.  
  
    -   Hem hizmet hem de hizmet arabirimi uygulayan bir sınıf.  
  
5.  Aşağıdaki örnek çok basit bir uygulama üç tür gösterir. Hizmet sınıf hizmet sağlayıcısı ayarlamanız gerekir. Bu örnekte, yalnızca hizmet paketi kod dosyasına ekleyeceğiz.  
  
6.  Aşağıdaki using deyimlerini paket dosyası:  
  
    ```csharp  
    using System.Threading;  
    using System.Threading.Tasks;  
    using System.Runtime.CompilerServices;  
    using System.IO;
    using Microsoft.VisualStudio.Threading;
    using IAsyncServiceProvider = Microsoft.VisualStudio.Shell.IAsyncServiceProvider;
    using Task = System.Threading.Tasks.Task;
    ```  
  
7.  Zaman uyumsuz hizmet uygulaması aşağıda verilmiştir. Zaman uyumlu bir hizmet sağlayıcısı yerine zaman uyumsuz hizmet sağlayıcısı oluşturucuda ayarlamak gerektiğini unutmayın:  
  
    ```csharp
    public class TextWriterService : STextWriterService, ITextWriterService  
    {  
        private IAsyncServiceProvider asyncServiceProvider;  
        
        public TextWriterService(IAsyncServiceProvider provider)  
        {
            // constructor should only be used for simple initialization
            // any usage of Visual Studio service, expensive background operations should happen in the
            // asynchronous InitializeAsync method for best performance
            asyncServiceProvider = provider;  
        }
        
        public async Task InitializeAsync(CancellationToken cancellationToken)
        {
            await TaskScheduler.Default;
            // do background operations that involve IO or other async methods

            await this.JoinableTaskFactory.SwitchToMainThreadAsync(cancellationToken);               
            // query Visual Studio services on main thread unless they are documented as free threaded explicitly.
            // The reason for this is the final cast to service interface (such as IVsShell) may involve COM operations to add/release references.

            IVsShell vsShell = this.asyncServiceProvider.GetServiceAsync(typeof(SVsShell)) as IVsShell;
            // use Visual Studio services to continue initialization
        }
        
        public async Task WriteLineAsync(string path, string line)  
        {  
            StreamWriter writer = new StreamWriter(path);  
            await writer.WriteLineAsync(line);  
            writer.Close();  
        }  
    }  

    public interface STextWriterService  
    {  
    }  
    
    public interface ITextWriterService   
    {  
        System.Threading.Tasks.Task WriteLineAsync(string path, string line);  
    }  
    ```  
  
## <a name="registering-a-service"></a>Bir hizmeti kaydetme  
 Bir hizmeti kaydetmek için ekleme <xref:Microsoft.VisualStudio.Shell.ProvideServiceAttribute> hizmeti sağlayan pakete. Farklı bir zaman uyumlu hizmeti kaydetme için paket ve hizmet yüklenirken zaman uyumsuz desteklediğinden emin olmak için gerekenler:
  
-   Eklemelisiniz **AllowsBackgroundLoading = true** alanı <xref:Microsoft.VisualStudio.Shell.PackageRegistrationAttribute> paket başlatılabilir, zaman uyumsuz olarak PackageRegistrationAttribute hakkında daha fazla bilgi sağlamak için bkz: [kaydetme ve Kaydı siliniyor VSPackages](../extensibility/registering-and-unregistering-vspackages.md).  
  
-   Eklemelisiniz **IsAsyncQueryable = true** alanı <xref:Microsoft.VisualStudio.Shell.ProvideServiceAttribute> hizmet örneği başlatılabilir, zaman uyumsuz olarak emin olmak için.

 Bir zaman uyumsuz hizmet kaydı ile bir AsyncPackage bir örneği burada verilmiştir:
  
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
  
    ```csharp
    protected override async Task InitializeAsync(CancellationToken cancellationToken, IProgress<ServiceProgressData> progress)  
    {  
        await base.InitializeAsync(cancellationToken, progress);  
        this.AddService(typeof(STextWriterService), CreateTextWriterService);
    }  
  
    ```  
  
2.  Microsoft.VisualStudio.Shell.Interop.14.0.DesignTime.dll bir başvuru ekleyin.  
  
3.  Geri çağırma yöntemi oluşturur ve hizmet döndüren zaman uyumsuz bir yöntem uygular.  
  
    ```csharp  
    public async Task<object> CreateTextWriterService(IAsyncServiceContainer container, CancellationToken cancellationToken, Type serviceType)  
    {  
        TextWriterService service = new TextWriterService(this);  
        await service.InitializeAsync(cancellationToken);
        return service;
    }  
  
    ```  
  
## <a name="using-a-service"></a>Bir hizmeti kullanma  
 Şimdi hizmetin ve yöntemlerini kullanın.  
  
1.  Bu Başlatıcı göstereceğiz, ancak herhangi bir yere hizmet kullanmak istediğiniz hizmet elde edebilirsiniz.  
  
    ```csharp  
    protected override async System.Threading.Tasks.Task InitializeAsync(CancellationToken cancellationToken, IProgress<ServiceProgressData> progress)  
    {  
        await base.InitializeAsync(cancellationToken, progress);  
        this.AddService(typeof(STextWriterService), CreateTextWriterService);  
  
        ITextWriterService textService = await this.GetServiceAsync(typeof(STextWriterService)) as ITextWriterService;  
  
        await textService.WriteLineAsync(<userpath>), "this is a test");  
    }  
  
    ```  
  
     Değiştirmeyi unutmayın  *\<userpath >* bir dosya adı ve makinenizde mantıklı yolu!  
  
2.  Derleme ve kodu çalıştırın. Visual Studio'nun deneysel örneği göründüğünde, bir çözüm açın. Bu autoload için AsyncPackage neden olur. Başlatıcı çalıştırıldığında, belirtilen konumda bir dosya bulmanız gerekir.  
  
## <a name="using-an-asynchronous-service-in-a-command-handler"></a>Zaman uyumsuz bir hizmet bir komut işleyici kullanma  
 Zaman uyumsuz bir hizmet bir menü komutunu kullanmak nasıl bir örneği burada verilmiştir. Diğer zaman uyumsuz olmayan yöntemlerle hizmeti kullanmak için burada gösterilen yordamı kullanabilirsiniz.  
  
1.  Menü komutu projenize ekleyin. (İçinde **Çözüm Gezgini**, proje düğümüne sağ tıklatın ve seçin seçin **Ekle / yeni öğe / genişletilebilirlik / özel komut**.) Komut dosyasının adı **TestAsyncCommand.cs.**  
  
2.  Özel komut şablonunu yeniden ekler `Initialize()` komutu başlatmak için TestAsyncPackage.cs dosyasına yöntemi. Önce Initialize() yöntemini başlatır komut satırı kopyalayın. Aşağıdaki gibi görünmelidir:  
  
    ```csharp
    TestAsyncCommand.Initialize(this);  
    ```  
  
     Bu satır taşıma `InitializeAsync()` AsyncPackageForService.cs dosyasındaki yöntemi. Zaman uyumsuz bir başlatma olduğundan komutunu kullanarak başlatılmadan önce ana iş parçacığına geçmelidir <xref:Microsoft.VisualStudio.Threading.JoinableTaskFactory.SwitchToMainThreadAsync%2A>. Bunu şu şekilde görünmelidir:  
  
    ```csharp  
  
    protected override async System.Threading.Tasks.Task InitializeAsync(CancellationToken cancellationToken, IProgress<ServiceProgressData> progress)  
    {  
        await base.InitializeAsync(cancellationToken, progress);  
        this.AddService(typeof(STextWriterService), CreateTextWriterService);  

        ITextWriterService textService =   
           await this.GetServiceAsync(typeof(STextWriterService)) as ITextWriterService;  
  
        await textService.WriteLineAsync((<userpath>, "this is a test");  
  
        await this.JoinableTaskFactory.SwitchToMainThreadAsync(cancellationToken);  
        TestAsyncCommand.Initialize(this);
    }  
  
    ```  
  
3.  Silme `Initialize()` yöntemi.  
  
4.  TestAsyncCommand.cs dosyasını bulun `MenuItemCallback()` yöntemi. Yönteminin gövdesi silin.  
  
5.  Kullanarak bir ekleme deyimi:  
  
    ```csharp 
    using System.IO;  
    ```  
  
6.  Adlı zaman uyumsuz bir yöntem eklemek `UseTextWriterAsync()`, hangi hizmet alır ve kendi yöntemleri kullanır:  
  
    ```csharp  
    private async System.Threading.Tasks.Task UseTextWriterAsync()  
    {  
        // Query text writer service asynchronously to avoid a blocking call.
        ITextWriterService textService =   
           await AsyncServiceProvider.GlobalProvider.GetServiceAsync(typeof(STextWriterService))  
              as ITextWriterService;  

        // don't forget to change <userpath> to a local path  
        await textService.WriteLineAsync((<userpath>),"this is a test");  
       }  
  
    ```  
  
7.  Bu yöntemi çağırın `MenuItemCallback()` yöntemi:  
  
    ```csharp
    private void MenuItemCallback(object sender, EventArgs e)  
    {  
        UseTextWriterAsync();  
    }  
  
    ```  
  
8.  Çözümü derlemek ve hata ayıklamayı Başlat. Visual Studio'nun deneysel örneği göründüğünde, Git **Araçları** menü ve Ara **çağırma TestAsyncCommand** menü öğesi. Tıklattığınızda, TextWriterService, belirtilen dosyaya yazar. (Komut çağırma Ayrıca paket yüklemek neden olduğundan, bir çözüm açmanız gerekmez.)  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Hizmetleri Kullanma ve Sağlama](../extensibility/using-and-providing-services.md)
