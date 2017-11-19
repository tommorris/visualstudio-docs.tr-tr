---
title: "Nasıl yapılır: bir hizmet sağlamak | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: services, providing
ms.assetid: 12bc1f12-47b1-44f6-b8db-862aa88d50d1
caps.latest.revision: "22"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: d0adc9f69f1b0e873d2e1f38c9317070dc0d6a08
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="how-to-provide-a-service"></a>Nasıl yapılır: bir hizmet sağlar
Bir VSPackage diğer VSPackages kullanabileceğiniz hizmetler sağlar. Bir hizmet sağlamak için bir VSPackage hizmeti ile Visual Studio kaydetmek ve hizmet eklemeniz gerekir.  
  
 <xref:Microsoft.VisualStudio.Shell.Package> Sınıfı uygulayan her ikisi de <xref:Microsoft.VisualStudio.OLE.Interop.IServiceProvider> ve <xref:System.ComponentModel.Design.IServiceContainer>. <xref:System.ComponentModel.Design.IServiceContainer>İsteğe bağlı hizmetleri sağlayan geri arama yöntemleri içerir.  
  
 Hizmetler hakkında daha fazla bilgi için bkz: [hizmet Essentials](../extensibility/internals/service-essentials.md) .  
  
> [!NOTE]
>  Bir VSPackage kaldırılmak üzere olduğunda, Visual Studio bir VSPackage sağladığı hizmetler için tüm istekleri teslim kadar bekler. Bu hizmetler için yeni istekleri izin vermiyor. Değil açıkça çağırmalıdır <xref:Microsoft.VisualStudio.Shell.Interop.IProfferService.RevokeService%2A> kaldırılması sırasında bir hizmeti iptal etmek için yöntem.  
  
#### <a name="implementing-a-service"></a>Bir hizmet uygulama  
  
1.  VSIX proje oluşturma (**dosya / yeni / Project / Visual C# / Extensiblity / VSIX proje**).  
  
2.  Bir VSPackage projeye ekleyin. Proje düğümünde seçin **Çözüm Gezgini** tıklatıp **Ekle / yeni öğe / Visual C# öğeleri / genişletilebilirlik / Visual Studio Paketi**.  
  
3.  Bir hizmet uygulamak için üç tür oluşturmanız gerekir:  
  
    -   Hizmet açıklayan bir arabirim. Bu arabirimleri çoğunu boş, diğer bir deyişle, yöntemlerin hiçbiri sahiptirler.  
  
    -   Hizmet arabirimi açıklayan bir arabirim. Bu arabirim, uygulanacak yöntemleri içerir.  
  
    -   Hem hizmet hem de hizmet arabirimi uygulayan bir sınıf.  
  
     Aşağıdaki örnek çok basit bir uygulama üç tür gösterir. Hizmet sınıf hizmet sağlayıcısı ayarlamanız gerekir.  
  
    ```csharp  
    public class MyService : SMyService, IMyService  
    {  
        private Microsoft.VisualStudio.OLE.Interop.IServiceProvider serviceProvider;  
        private string myString;  
        public MyService(Microsoft.VisualStudio.OLE.Interop.IServiceProvider sp)  
        {  
            Trace.WriteLine(  
                   "Constructing a new instance of MyService");  
            serviceProvider = sp;  
        }  
        public void Hello()  
        {  
            myString = "hello";  
        }  
        public string Goodbye()  
        {  
           return "goodbye";  
        }  
    }  
    public interface SMyService  
    {  
    }  
    public interface IMyService  
    {  
        void Hello();  
        string Goodbye();  
    }  
  
    ```  
  
### <a name="registering-a-service"></a>Bir hizmeti kaydetme  
  
1.  Bir hizmeti kaydetmek için ekleme <xref:Microsoft.VisualStudio.Shell.ProvideServiceAttribute> hizmeti sağlayan VSPackage için. Aşağıda bir örnek verilmiştir:  
  
    ```csharp  
    [ProvideService(typeof(SMyService))]  
    [PackageRegistration(UseManagedResourcesOnly = true)]  
    [Guid(VSPackage1.PackageGuidString)]  
    public sealed class VSPackage1 : Package  
    {. . . }  
    ```  
  
     Bu öznitelik kaydeder `SMyService` Visual Studio ile.  
  
    > [!NOTE]
    >  Aynı ada sahip başka bir hizmeti yerine bir hizmet kaydetmek için kullanın <xref:Microsoft.VisualStudio.Shell.ProvideServiceOverrideAttribute>. Not bir hizmetin yalnızca bir bu geçersiz kılma izin verilir.  
  
### <a name="adding-a-service"></a>Bir hizmet ekleme  
  
1.  VSPackage Başlatıcı Hizmeti ekleyin ve hizmetleri oluşturmak için bir geri çağırma yöntemi ekleyin. Değişiklik yapmak için işte <xref:Microsoft.VisualStudio.Shell.Package.Initialize%2A> yöntemi:  
  
    ```csharp  
    protected override void Initialize()  
    {  
        ServiceCreatorCallback callback =new ServiceCreatorCallback(CreateService);  
  
        ((IServiceContainer)this).AddService(typeof(SMyService), callback);  
    . . .  
    }  
    ```  
  
2.  , Oluşturma ve hizmet döndürür veya onu oluşturulamazsa null geri çağırma yöntemini uygulayın.  
  
    ```  
    private object CreateService(IServiceContainer container, Type serviceType)  
    {  
        if (typeof(SMyService) == serviceType)  
            return new SMyService(this);  
        return null;  
    }  
    ```  
  
    > [!NOTE]
    >  Visual Studio, bir hizmet sağlamak için bir istek reddedebilirsiniz. Hizmet zaten başka bir VSPackage sağlıyorsa, bunu yapar.  
  
3.  Şimdi hizmetin ve yöntemlerini kullanın. Bu Başlatıcı göstereceğiz, ancak herhangi bir yere hizmet kullanmak istediğiniz hizmet elde edebilirsiniz.  
  
    ```csharp  
    protected override void Initialize()  
    {  
        ServiceCreatorCallback callback =new ServiceCreatorCallback(CreateService);  
  
        ((IServiceContainer)this).AddService(typeof(SMyService), callback);  
  
        MyService myService = (MyService) this.GetService(typeof(SMyService));  
        myService.Hello();  
        string helloString = myService.myString;  
  
        base.Initialize();  
    }  
    ```  
  
     Değeri `helloString` "Hello" olmalıdır.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Nasıl yapılır: bir hizmeti Al](../extensibility/how-to-get-a-service.md)   
 [Kullanarak ve hizmetleri sağlar](../extensibility/using-and-providing-services.md)   
 [Hizmet temelleri](../extensibility/internals/service-essentials.md)