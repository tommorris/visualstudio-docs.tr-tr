---
title: "Komut uygulaması | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- commands, implementation
ms.assetid: c782175c-cce4-4bd0-8374-4a897ceb1b3d
caps.latest.revision: 
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload:
- vssdk
ms.openlocfilehash: 2704794e4683fb461dca971a3893ca831591ca0c
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="command-implementation"></a>Komut uygulama
Bir komut bir VSPackage uygulamak için aşağıdaki görevleri gerçekleştirmeniz gerekir:  
  
1.  .Vsct dosyasında bir komut grubu oluşturun ve komut ekleyin. Daha fazla bilgi için bkz: [Visual Studio komut tablosu (. Vsct) dosyaları](../../extensibility/internals/visual-studio-command-table-dot-vsct-files.md)'  
  
2.  Visual Studio ile register komutu.  
  
3.  Komut uygulayın.  
  
 Aşağıdaki bölümlerde, kaydetme ve komutları uygulamak açıklanmaktadır.  
  
## <a name="registering-commands-with-visual-studio"></a>Visual Studio ile komutları kaydetme  
 Komutunuz menüde görünür olup olmadığını, eklemelisiniz <xref:Microsoft.VisualStudio.Shell.ProvideMenuResourceAttribute> VSPackage ve menünün adını ya da kaynak kimliğini bir değer olarak kullanmak için  
  
```  
[ProvideMenuResource("Menus.ctmenu", 1)]  
...  
    public sealed class MyPackage : Package  
    {.. ..}  
  
```  
  
 Ayrıca, komutu ile kaydetmeniz gerekir <xref:Microsoft.VisualStudio.Shell.OleMenuCommandService>. Bu hizmeti kullanarak alabileceğiniz <xref:Microsoft.VisualStudio.Shell.Package.GetService%2A> , VSPackage türetilir varsa yöntemi <xref:Microsoft.VisualStudio.Shell.Package>.  
  
```  
OleMenuCommandService mcs = GetService(typeof(IMenuCommandService)) as OleMenuCommandService;  
if ( null != mcs )  
{  
    // Create the command for the menu item.  
    CommandID menuCommandID = new CommandID(guidCommandGroup, myCommandID);  
    MenuCommand menuItem = new MenuCommand(MenuItemCallback, menuCommandID );  
    mcs.AddCommand( menuItem );  
}  
  
```  
  
## <a name="implementing-commands"></a>Komutları uygulama  
 Bir komutları uygulamak için çeşitli yöntemler vardır. Her zaman aynı şekilde ve aynı menüsünde görünen komut olduğundan, statik menü komutu istiyorsanız komutu kullanarak Oluştur <xref:System.ComponentModel.Design.MenuCommand> önceki bölümdeki örneklerde gösterildiği gibi. Statik bir komut oluşturmak için komutu yürütmek için sorumlu olduğu bir olay işleyicisi sağlamanız gerekir. Komut, her zaman etkin ve görünür olduğundan, durumunu sağlamak için Visual Studio gerekmez. Belirli koşullara bağlı olarak bir komut durumunu değiştirmek istiyorsanız, komut örneği oluşturabileceğiniz <xref:Microsoft.VisualStudio.Shell.OleMenuCommand> sınıfı ve kurucusunda, komutu çalıştırmak için bir olay işleyicisi ve Visual bildirmek üzere bir sorgu durumu işleyici sağlayın Komut durumu değiştiğinde studio. Ayrıca uygulayabilirsiniz <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget> komut sınıfı veya, parçası uygulayabilirsiniz gibi <xref:Microsoft.VisualStudio.Shell.Interop.IVsHierarchy> bir projenin bir parçası bir komut sağlıyorsanız. İki arabirim ve <xref:Microsoft.VisualStudio.Shell.OleMenuCommand> sınıfı tüm Visual Studio komut durum değişikliği bildirim yöntemleri, komutun yürütülmesi sağlayan ve diğer yöntemleri vardır.  
  
 Bir komut komut hizmetine eklendiğinde, komutları zinciri birini olur. Durum bildirim ve yürütme yöntemleri komutu için uyguladığınızda, o belirli komut için yalnızca sağlamak ve diğer komutları açın tüm diğer durumlarda zincirde geçirmek için dikkatli olun. Komut geçmesine başarısız olursa (genellikle döndürme tarafından <xref:Microsoft.VisualStudio.OLE.Interop.Constants>), Visual Studio düzgün çalışmasını durdurabilir.  
  
## <a name="query-status-methods"></a>Sorgu durumu yöntemleri  
 Ya da uyguluyorsanız <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget.QueryStatus%2A> yöntemi veya <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIHierarchy.QueryStatusCommand%2A> yöntemi, komut ait olduğu set komutu GUID denetle ve komut kimliği. Aşağıdaki yönergeleri izleyin:  
  
-   GUID, tanınmıyor, her iki yöntem uygulanmasını döndürmelidir <xref:Microsoft.VisualStudio.OLE.Interop.Constants>.  
  
-   Her iki yöntem uygulanmasını GUID algılar, ancak komut gerçekte uygulanmadı durumunda yöntem döndürmelidir <xref:Microsoft.VisualStudio.OLE.Interop.Constants>.  
  
-   Her iki yöntem uygulanmasını GUID ve komut tanıdığı sonra yöntemi her komutun komut bayrak alanı ayarlamanız gerekir (içinde `prgCmds` parametresi) aşağıdaki bayraklar kullanarak:  
  
    -   <xref:Microsoft.VisualStudio.OLE.Interop.OLECMDF>komut destekleniyorsa.  
  
    -   <xref:Microsoft.VisualStudio.OLE.Interop.OLECMDF>komut görünür olmamalıdır.  
  
    -   <xref:Microsoft.VisualStudio.OLE.Interop.OLECMDF>Komut çubuğunda yükseğe ve denetlendi gibi görünüyor  
  
    -   <xref:Microsoft.VisualStudio.OLE.Interop.OLECMDF>komutu etkin olduğunda.  
  
    -   <xref:Microsoft.VisualStudio.OLE.Interop.OLECMDF>kısayol menüsünde görünen komut gizli.  
  
    -   <xref:Microsoft.VisualStudio.OLE.Interop.OLECMDF>komut bir menü denetleyicisidir ve etkin değil, ancak kendi açılır menü listesi boş değil ve hala kullanılabilir olması gerekir. (Bu bayrak nadiren kullanılır.)  
  
-   Komut dosyasında, .vsct tanımlanmışsa, `TextChanges` bayrağı, aşağıdaki parametreleri ayarlayın:  
  
    -   Ayarlama `rgwz` öğesinin `pCmdText` yeni metin komut parametresi.  
  
    -   Ayarlama `cwActual` öğesinin `pCmdText` komutu dize boyutu parametresi.  
  
 Ayrıca komutunuzu özellikle Otomasyon işlevleri işlemek için tasarlanmıştır sürece geçerli bağlamı bir Otomasyon işlevi olmadığından emin olun.  
  
 Belirli bir komut desteği belirtmek için iade <xref:Microsoft.VisualStudio.VSConstants.S_OK>. Diğer tüm komutlar için iade <xref:Microsoft.VisualStudio.OLE.Interop.Constants>.  
  
 Aşağıdaki örnekte, sorgu status yöntemi önce bağlamı bir Otomasyon işlevi değil, sonra komut kimliği ve doğru komut kümesini GUID bulur emin olur Komutu etkin ve desteklenen ayarlanır. Başka hiçbir komut desteklenir.  
  
```  
public int QueryStatus(ref Guid pguidCmdGroup, uint cCmds, OLECMD[] prgCmds, IntPtr pCmdText)  
{  
    if (!VsShellUtilities.IsInAutomationFunction(m_provider.ServiceProvider))  
    {  
        if (pguidCmdGroup == VSConstants.VSStd2K && cCmds > 0)  
        {  
            // make the Right command visible   
            if ((uint)prgCmds[0].cmdID == (uint)VSConstants.VSStd2KCmdID.RIGHT)  
            {  
                prgCmds[0].cmdf = (int)Microsoft.VisualStudio.OLE.Interop.Constants.MSOCMDF_ENABLED | (int)Microsoft.VisualStudio.OLE.Interop.Constants.MSOCMDF_SUPPORTED;  
                return VSConstants.S_OK;  
            }  
        }  
        return Constants.OLECMDERR_E_NOTSUPPORTED;  
    }  
}  
  
```  
  
## <a name="execution-methods"></a>Yürütme yöntemleri  
 Execute yöntemi uyarlamasını sorgu durumu yöntemin kullanımı benzer. İlk olarak, bağlam bir Otomasyon işlevi olmadığından emin olun. GUID ve komut kimliği için test Varsa GUID veya komut kimliği tanınmıyor, iade <xref:Microsoft.VisualStudio.OLE.Interop.Constants>.  
  
 Komutu işlemek için çalıştırmak ve dönüş <xref:Microsoft.VisualStudio.VSConstants.S_OK> yürütme başarılı olursa. Komutunuzu hata algılama ve bildirim sorumludur; Bu nedenle, yürütme başarısız olursa bir hata kodunu döndürür. Aşağıdaki örnek, yürütme yönteminin nasıl uygulanması gösterir.  
  
```  
public int Exec(ref Guid pguidCmdGroup, uint nCmdID, uint nCmdexecopt, IntPtr pvaIn, IntPtr pvaOut)  
{  
    if (!VsShellUtilities.IsInAutomationFunction(m_provider.ServiceProvider))  
    {  
        if (pguidCmdGroup == VSConstants.GUID_VSStandardCommandSet97)  
        {  
             if (nCmdID ==(uint) uint)VSConstants.VSStd2KCmdID.RIGHT)  
            {  
                //execute the command  
                return VSConstants.S_OK;  
            }  
        }  
    }  
    return Constants.OLECMDERR_E_NOTSUPPORTED;  
}  
  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [VSPackage’ların Kullanıcı Arabirimi Öğeleri Eklemesi](../../extensibility/internals/how-vspackages-add-user-interface-elements.md)