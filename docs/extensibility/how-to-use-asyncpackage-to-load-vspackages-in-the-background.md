---
title: "Nasıl yapılır: arka planda VSPackages yüklemek için AsyncPackage kullanın | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: dedf0173-197e-4258-ae5a-807eb3abc952
caps.latest.revision: "8"
author: gregvanl
ms.author: gregvanl
ms.openlocfilehash: b89f021b181e653dff97368cc5c1f2d993f04323
ms.sourcegitcommit: f36eb7f989efbdbed0d0a087afea8ffe27d8ca15
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/14/2017
---
# <a name="how-to-use-asyncpackage-to-load-vspackages-in-the-background"></a>Nasıl yapılır: arka planda VSPackages yüklemek için AsyncPackage kullanın
Yükleme ve VS Paketi başlatma disk g/ç neden olabilir. Bu tür g/ç kullanıcı Arabirimi iş parçacığı üzerinde olursa, yanıt hızını sorunlarına yol açabilir. Bu sorunu çözmek için Visual Studio 2015 sunulan <xref:Microsoft.VisualStudio.Shell.AsyncPackage> paketi yükleme arka plan iş parçacığında sağlayan sınıf.  
  
## <a name="creating-an-asyncpackage"></a>Bir AsyncPackage oluşturma  
 Bir VSIX projesi oluşturarak başlayın (**Dosya > Yeni > Proje > Visual C# > genişletilebilirlik > VSIX proje**) ve bir VSPackage projeye ekleme (projeye sağ tıklayın ve **Ekle/yeni öğe / C# öğesi / Extensibility/Visual Studio Paketi**). Ardından, hizmetlerinizi oluşturun ve bu hizmetleri paketinize ekleyin.  
  
1.  Paketten türetilen <xref:Microsoft.VisualStudio.Shell.AsyncPackage>.  
  
2.  Hizmetleri, sorgulama paketinizi yüklemek neden olabilecek sağlıyorsanız:  
  
     Visual Studio paketinizi arka planda yükleme için güvenli olduğunu göstermek için ve bu davranış kabul etmek için <xref:Microsoft.VisualStudio.Shell.PackageRegistrationAttribute> ayarlamalısınız **AllowsBackgroundLoading** özelliğinin öznitelik oluşturucuda true.  
  
    ```csharp  
    [PackageRegistration(UseManagedResourcesOnly = true, AllowsBackgroundLoading = true)]  
  
    ```  
  
     Visual Studio için bir arka plan iş parçacığı hizmet örneği oluşturmak güvenli olduğunu belirtmek için ayarlamalısınız <xref:Microsoft.VisualStudio.Shell.ProvideServiceAttributeBase.IsAsyncQueryable%2A> özelliğini true <xref:Microsoft.VisualStudio.Shell.ProvideServiceAttribute> Oluşturucusu.  
  
    ```csharp  
    [ProvideService(typeof(SMyTestService), IsAsyncQueryable = true)]  
  
    ```  
  
3.  UI bağlamları yüklenen sonra belirtmeniz gerekir **PackageAutoLoadFlags.BackgroundLoad** için <xref:Microsoft.VisualStudio.Shell.ProvideAutoLoadAttribute> veya bayrak değeri (0x2), paketin otomatik yük giriş değeri olarak yazılır.  
  
    ```csharp  
    [ProvideAutoLoad(UIContextGuid, PackageAutoLoadFlags.BackgroundLoad)]  
  
    ```  
  
4.  Zaman uyumsuz başlatma işini yapmak için varsa, geçersiz kılmalısınız <xref:Microsoft.VisualStudio.Shell.AsyncPackage.InitializeAsync%2A>. Kaldırma **Initialize()** VSIX şablon tarafından sağlanan yöntemi. ( **Initialize()** yönteminde **AsyncPackage** korumalı değil). Herhangi birini kullanabilmeniz için <xref:Microsoft.VisualStudio.Shell.AsyncPackage.AddService%2A> yöntemleri zaman uyumsuz hizmet paketinize ekleyin.  
  
     Not: çağırmak için **temel. InitializeAsync()**, kaynak kodunuzu değiştirebilirsiniz:  
  
    ```csharp  
    await base.InitializeAsync(cancellationToken, progress);  
    ```  
  
5.  RPC (uzak yordam çağrısı) yapmamak için zaman uyumsuz başlatma kodunuzdan ilgilenebilmek gerekir (içinde **InitializeAsync**). Çağırdığınızda bunlar oluşabilir <xref:Microsoft.VisualStudio.Shell.Package.GetService%2A> doğrudan veya dolaylı olarak.  Eşitleme yükleri gerekli olduğunda, kullanıcı Arabirimi iş parçacığı kullanan engeller <xref:Microsoft.VisualStudio.Threading.JoinableTaskFactory>. Varsayılan engelleme modeli RPC'ler devre dışı bırakır. Bu, zaman uyumsuz görevleri bir RPC kullanmayı denerseniz, kullanıcı Arabirimi iş parçacığı kendini yüklemeye paketiniz için bekleyen ise, kilitlenme, anlamına gelir. Kullanıcı Arabirimi iş parçacığı kodunuzu şöyle kullanarak gerekirse sıralamakta genel alternatiftir **birleştirilebilir görev Fabrika**'s <xref:Microsoft.VisualStudio.Threading.JoinableTaskFactory.SwitchToMainThreadAsync%2A> veya bir RPC kullanmaz başka bir mekanizma.  Kullanmayın **ThreadHelper.Generic.Invoke** veya genellikle için kullanıcı Arabirimi iş parçacığı bekleniyor çağıran iş parçacığı engelleyin.  
  
     Not: Yapmaktan kaçınmalısınız **GetService** veya **QueryService** içinde **InitializeAsync** yöntemi. Bu kullanmanız gerekiyorsa, kullanıcı Arabirimi iş parçacığı için önce geçmesi gerekir. Alternatif kullanmaktır <xref:Microsoft.VisualStudio.Shell.AsyncServiceProvider.GetServiceAsync%2A> gelen, **AsyncPackage** (kendisine atama tarafından <xref:Microsoft.VisualStudio.Shell.Interop.IAsyncServiceProvider>.)  
  
 C# ' ta: bir AsyncPackage oluşturun:  
  
```csharp  
[PackageRegistration(UseManagedResourcesOnly = true, AllowsBackgroundLoading = true)]       
[ProvideService(typeof(SMyTestService), IsAsyncQueryable = true)]   
public sealed class TestPackage : AsyncPackage   
{   
    protected override Task InitializeAsync(System.Threading.CancellationToken cancellationToken, IProgress<ServiceProgressData> progress)   
    {               
        this.AddService(typeof(SMyTestService), CreateService, true);   
        return Task.FromResult<object>(null);   
    }   
}  
```  
  
## <a name="convert-an-existing-vspackage-to-asyncpackage"></a>Varolan bir VSPackage AsyncPackage için Dönüştür  
 İş çoğunluğu yeni oluşturma aynıdır **AsyncPackage**. 1 ile 5 yukarıdaki adımları izlemeniz gerekir. Ayrıca çok dikkatli aşağıdakilere olması gerekir:  
  
1.  Kaldırmayı unutmayın **başlatma** geçersiz kılma paketinize vardı.  
  
2.  Kilitlenmeler kaçının: olabilir şimdi arka plan iş parçacığında olabileceği kodunuzda RPC'ler gizli. Bir RPC yapıyorsanız emin olmanız gerekir (örneğin **GetService**), ana iş parçacığı (1) ya da anahtara gerek veya (2) kullanım zaman uyumsuz bir API sürümü var (örneğin **GetServiceAsync**).  
  
3.  Çok sık iş parçacıkları arasında geçiş değil. Arka plan iş parçacığında oluşabilir iş yerelleştirme deneyin. Bu yükleme süresini azaltır.  
  
## <a name="querying-services-from-asyncpackage"></a>AsyncPackage Hizmetleri'nden sorgulama  
 Bir **AsyncPackage** olabilir veya zaman uyumsuz olarak bağlı olarak çağıran yüklenmeyebilir. Örneğin,  
  
-   Arayan çağrıldıklarında **GetService** veya **QueryService** (her iki zaman uyumlu API) veya  
  
-   Arayan çağrıldıklarında **IVsShell::LoadPackage** (veya **IVsShell5::LoadPackageWithContext**) veya  
  
-   Yük UI bağlam tarafından tetiklenir ancak kullanıcı Arabirimi bağlam mekanizması, zaman uyumsuz olarak yükleyebilirsiniz belirtmedi  
  
 Ardından, paketi zaman uyumlu olarak yükler.  
  
 Kullanıcı Arabirimi iş parçacığı için çalışan kişinin tamamlama engellenecek olsa paketinizi hala fırsatı (zaman uyumsuz başlangıç aşamasında) kullanıcı Arabirimi iş parçacığı devre dışı çalışmaya olduğuna dikkat edin. Arayan kullanıyorsa **IAsyncServiceProvider** hizmetiniz için zaman uyumsuz olarak sorgu için sonra yükleme ve başlatma zaman uyumsuz olarak bunlar yok hemen engellemek sonuçta elde edilen görev nesnede varsayılarak yapılacaktır.  
  
 C# ' ta: hizmet zaman uyumsuz olarak nasıl:  
  
```csharp  
using Microsoft.VisualStudio.Shell;   
using Microsoft.VisualStudio.Shell.Interop;   
  
IAsyncServiceProvider asyncServiceProvider = Package.GetService(typeof(SAsyncServiceProvider)) as IAsyncServiceProvider;   
IMyTestService testService = await ayncServiceProvider.GetServiceAsync(typeof(SMyTestService)) as IMyTestService;  
```
  
