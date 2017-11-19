---
title: "&lt;trustInfo&gt; öğesi (ClickOnce uygulaması) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-deployment
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- urn:schemas-microsoft-com:asm.v2#IPermission
- urn:schemas-microsoft-com:asm.v2#PermissionSet
- urn:schemas-microsoft-com:asm.v2#assemblyRequest
- urn:schemas-microsoft-com:asm.v2#trustInfo
- urn:schemas-microsoft-com:asm.v2#defaultAssemblyRequest
- urn:schemas-microsoft-com:asm.v2#security
dev_langs:
- VB
- CSharp
- C++
helpviewer_keywords:
- manifests [ClickOnce], trustInfo element
- <trustInfo> element [ClickOnce application manifest]
ms.assetid: 8a813a74-e158-4308-be78-565937f6af83
caps.latest.revision: "16"
author: stevehoag
ms.author: shoag
manager: wpickett
ms.openlocfilehash: 645d4252dd13f4e4629d1ab636ad8b85142242c2
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
---
# <a name="lttrustinfogt-element-clickonce-application"></a>&lt;trustInfo&gt; öğesi (ClickOnce uygulaması)
Uygulamanın istemci bilgisayarda çalışması gerekli en düşük güvenlik izinleri açıklar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
      <trustInfo>  
   <security>  
      <applicationRequestMinimum>  
         <PermissionSet  
            ID  
            Unrestricted>  
            <IPermission  
               class  
               version  
               Unrestricted  
            />  
         </PermissionSet>  
         <defaultAssemblyRequest  
            permissionSetReference  
         />  
         <assemblyRequest  
            name  
            permissionSetReference  
         />  
      </applicationRequestMinimum>  
      <requestedPrivileges>  
         <requestedExecutionLevel  
            level  
            uiAccess  
         />  
      </requestedPrivileges>  
   </security>  
</trustInfo>  
```  
  
## <a name="elements-and-attributes"></a>Öğeleri ve öznitelikleri  
 `trustInfo` Öğesi gereklidir ve yer `asm.v2` ad alanı. Özniteliklere sahip ve aşağıdaki öğeleri içerir.  
  
## <a name="security"></a>güvenlik  
 Gerekli. Bu öğe bir alt öğesi değil `trustInfo` öğesi. İçerdiği `applicationRequestMinimum` öğesi ve özniteliklere sahiptir.  
  
## <a name="applicationrequestminimum"></a>applicationRequestMinimum  
 Gerekli. Bu öğe bir alt öğesi değil `security` öğesi ve içeren `PermissionSet`, `assemblyRequest`, ve `defaultAssemblyRequest`öğeleri. Bu öğe özniteliklere sahiptir.  
  
## <a name="permissionset"></a>PermissionSet  
 Gerekli. Bu öğe bir alt öğesi değil `applicationRequestMinimum` öğesi ve içeren `IPermission` öğesi. Bu öğe aşağıdaki özniteliklere sahiptir.  
  
-   `ID`  
  
     Gerekli. İzin kümesi tanımlar. Bu öznitelik, herhangi bir değer olabilir. Kimliği başvuru `defaultAssemblyRequest` ve `assemblyRequest` öznitelikleri.  
  
-   `version`  
  
     Gerekli. İzin sürümünü tanımlar. Bu değer normalde olur `1`.  
  
## <a name="ipermission"></a>IPermission  
 İsteğe bağlı. Bu öğe bir alt öğesi değil `PermissionSet` öğesi. `IPermission` Öğesi tam olarak içinde izin sınıfını tanımlar [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)]. `IPermission` Öğesi izin sınıfından özelliklere karşılık gelen ek öznitelikler aşağıdaki özniteliklere sahip, ancak. Belirli bir izin sözdizimi öğrenmek için Security.config dosyasında listelenen örneklere bakın.  
  
-   `class`  
  
     Gerekli. İzin sınıfını güçlü adıyla tanımlar. Örneğin, aşağıdaki kodu tanımlayan `FileDialogPermission` türü.  
  
     `System.Security.Permissions.FileDialogPermission, mscorlib, Version=1.2.3300.0, Culture=neutral, PublicKeyToken=b77a5c561934e089`  
  
-   `version`  
  
     Gerekli. İzin sürümünü tanımlar. Bu değer genellikle olur `1`.  
  
-   `Unrestricted`  
  
     Gerekli. Uygulamanın bu izni sınırsız bir verme ihtiyacı olup olmadığını tanımlar. Varsa `true`, izin verme koşulsuz olur. Varsa `false`, ya da bu öznitelik tanımlanmamışsa, tanımlanan izne özel özniteliklere göre kısıtlı `IPermission` etiketi. Aşağıdaki izinleri alın:  
  
    ```  
    <IPermission  
      class="System.Security.Permissions.EnvironmentPermission, mscorlib, Version=1.2.3300.0, Culture=neutral, PublicKeyToken=b77a5c561934e089"   
      version="1"   
      Read="USERNAME" />  
    <IPermission  
      class="System.Security.Permissions.FileDialogPermission, mscorlib, Version=1.2.3300.0, Culture=neutral, PublicKeyToken=b77a5c561934e089"   
      version="1"   
      Unrestricted="true" />  
    ```  
  
     Bu örnekte, bildirimi <xref:System.Security.Permissions.EnvironmentPermission> ise yalnızca ortam değişkeni kullanıcı adı, okuma uygulamanın kısıtlayan bildirimi <xref:System.Security.Permissions.FileDialogPermission> tüm Kısıtlanmamış uygulama kullanımını verir <xref:System.Windows.Forms.FileDialog> sınıfları.  
  
## <a name="defaultassemblyrequest"></a>defaultAssemblyRequest  
 İsteğe bağlı. Tüm derlemelere verilen izinler kümesini tanımlar. Bu öğe bir alt öğesi değil `applicationRequestMinimum` öğesi ve aşağıdaki özniteliklere sahiptir.  
  
-   `permissionSetReference`  
  
     Gerekli. Varsayılan izni izin kümesi Kimliğini tanımlar. İzin kümesi içinde bildirilen `PermissionSet` öğesi.  
  
## <a name="assemblyrequest"></a>assemblyRequest  
 İsteğe bağlı. Belirli bir derleme için izinleri tanımlar. Bu öğe bir alt öğesi değil `applicationRequestMinimum` öğesi ve aşağıdaki özniteliklere sahiptir.  
  
-   `Name`  
  
     Gerekli. Derleme adını tanımlar.  
  
-   `permissionSetReference`  
  
     Gerekli. Bu derleme gerektiriyor izin kümesi Kimliğini tanımlar. İzin kümesi içinde bildirilen `PermissionSet` öğesi.  
  
## <a name="requestedprivileges"></a>requestedPrivileges  
 İsteğe bağlı. Bu öğe bir alt öğesi değil `security` öğesi ve içeren `requestedExecutionLevel` öğesi. Bu öğe özniteliklere sahiptir.  
  
## <a name="requestedexecutionlevel"></a>requestedExecutionLevel  
 İsteğe bağlı. Uygulama yürütülebilir ister güvenlik düzeyini tanımlar. Bu öğenin alt öğesi yok ve aşağıdaki özniteliklere sahiptir.  
  
-   `Level`  
  
     Gerekli. Güvenlik düzeyi uygulama isteyen gösterir. Olası değerler şunlardır:  
  
     `asInvoker`, ek izinler istenmez. Bu düzey ek güven istekleri gerektirir.  
  
     `highestAvailable`, üst işlemi için kullanılabilir en yüksek izinleri istiyor.  
  
     `requireAdministrator`, tam yönetici izinleri istenir.  
  
     [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)]uygulamaları yalnızca bir değeri ile yükleme `asInvoker`. Herhangi bir değeri ile yükleme başarısız olur.  
  
-   `uiAccess`  
  
     İsteğe bağlı. Uygulamanın korumalı kullanıcı arabirimi öğeleri erişim ihtiyacı olup olmadığını gösterir. Değerler: ya da `true` veya `false`, ve varsayılan değer false. Yalnızca imzalı uygulamaları true değeri olmalıdır.  
  
## <a name="remarks"></a>Açıklamalar  
 Varsa bir [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] uygulama, varsayılan olarak, uygulamayı yükseltilmiş düzeyi güven verme durumunda istediği zamanının güven yöneticisi kullanıcı sorar ortak dil istemci bilgisayarın vereceği daha fazla izin sorar. Kullanıcı hayır derse uygulama çalışmaz; Aksi halde, istenen izinlerle çalışacaktır.  
  
 Kullanılarak istenilen tüm izinler `defaultAssemblyRequest` ve `assemblyRequest` dağıtım bildiriminin geçerli bir güven lisansı varsa, kullanıcıya sorulmadan verilecektir.  
  
 İzin yükseltme hakkında daha fazla bilgi için bkz: [ClickOnce uygulamalarının güvenliğini sağlama](../deployment/securing-clickonce-applications.md). Dağıtım ilkesi hakkında daha fazla bilgi için bkz: [güvenilir uygulama dağıtımına genel bakış](../deployment/trusted-application-deployment-overview.md).  
  
## <a name="examples"></a>Örnekler  
 Aşağıdaki üç kod örnekleri göstermeye `trustInfo` varsayılan olarak adlandırılan güvenlik bölgeleri için öğeleri — Internet, LocalIntranet ve FullTrust — kullanılmak üzere bir [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] dağıtımın uygulama bildirimi.  
  
 İlk örnek gösterilmektedir `trustInfo` Internet güvenlik bölgesi'teki varsayılan izinler için öğesi.  
  
```  
<trustInfo>  
    <security>  
      <applicationRequestMinimum>  
        <PermissionSet ID="Internet">  
          <IPermission  
            class="System.Security.Permissions.FileDialogPermission, mscorlib, Version=1.2.3300.0, Culture=neutral, PublicKeyToken=b77a5c561934e089"  
            version="1"   
            Access="Open" />  
          <IPermission  
           class="System.Security.Permissions.IsolatedStorageFilePermission, mscorlib, Version=1.2.3300.0, Culture=neutral, PublicKeyToken=b77a5c561934e089"   
            version="1"  
            Allowed="DomainIsolationByUser"  
            UserQuota="10240" />  
          <IPermission  
            class="System.Security.Permissions.SecurityPermission, mscorlib, Version=1.2.3300.0, Culture=neutral, PublicKeyToken=b77a5c561934e089"  
            version="1"   
            Flags="Execution" />  
          <IPermission   
            class="System.Security.Permissions.UIPermission, mscorlib, Version=1.2.3300.0, Culture=neutral, PublicKeyToken=b77a5c561934e089"   
            version="1"   
            Window="SafeTopLevelWindows"  
            Clipboard="OwnClipboard" />  
          <IPermission  
            class="System.Drawing.Printing.PrintingPermission, System.Drawing, Version=1.2.3300.0, Culture=neutral, PublicKeyToken=b03f5f7f11d50a3a"  
            version="1"   
            Level="SafePrinting" />  
        </PermissionSet>  
        <defaultAssemblyRequest permissionSetReference="Internet" />  
      </applicationRequestMinimum>  
    </security>  
  </trustInfo>  
```  
  
 İkinci örnek gösterilmektedir `trustInfo` LocalIntranet güvenlik bölgesinde varsayılan izinler için öğesi.  
  
```  
<trustInfo>  
    <security>  
      <applicationRequestMinimum>  
        <PermissionSet ID="LocalIntranet">  
          <IPermission  
            class="System.Security.Permissions.EnvironmentPermission, mscorlib, Version=1.2.3300.0, Culture=neutral, PublicKeyToken=b77a5c561934e089"   
            version="1"   
            Read="USERNAME" />  
          <IPermission  
            class="System.Security.Permissions.FileDialogPermission, mscorlib, Version=1.2.3300.0, Culture=neutral, PublicKeyToken=b77a5c561934e089"   
            version="1"   
            Unrestricted="true" />  
          <IPermission  
            class="System.Security.Permissions.IsolatedStorageFilePermission, mscorlib, Version=1.2.3300.0, Culture=neutral, PublicKeyToken=b77a5c561934e089"   
            version="1"   
            Allowed="AssemblyIsolationByUser"  
            UserQuota="9223372036854775807"  
            Expiry="9223372036854775807"  
            Permanent="True" />  
          <IPermission  
            class="System.Security.Permissions.ReflectionPermission, mscorlib, Version=1.2.3300.0, Culture=neutral, PublicKeyToken=b77a5c561934e089"   
            version="1"   
            Flags="ReflectionEmit" />  
          <IPermission  
            class="System.Security.Permissions.SecurityPermission, mscorlib, Version=1.2.3300.0, Culture=neutral, PublicKeyToken=b77a5c561934e089"   
            version="1"   
            Flags="Assertion, Execution" />  
          <IPermission   
            class="System.Security.Permissions.UIPermission, mscorlib, Version=1.2.3300.0, Culture=neutral, PublicKeyToken=b77a5c561934e089"  
            version="1"   
            Unrestricted="true" />  
          <IPermission  
            class="System.Net.DnsPermission, System, Version=1.2.3300.0, Culture=neutral, PublicKeyToken=b77a5c561934e089"  
            version="1"   
            Unrestricted="true" />  
          <IPermission  
            class="System.Drawing.Printing.PrintingPermission, System.Drawing, Version=1.2.3300.0, Culture=neutral, PublicKeyToken=b03f5f7f11d50a3a"  
            version="1"  
            Level="DefaultPrinting" />  
          <IPermission  
            class="System.Diagnostics.EventLogPermission, System, Version=1.2.3300.0, Culture=neutral, PublicKeyToken=b77a5c561934e089"  
            version="1" />  
        </PermissionSet>  
        <defaultAssemblyRequest permissionSetReference="LocalIntranet" />  
      </applicationRequestMinimum>  
    </security>  
</trustInfo>  
```  
  
 Üçüncü örnek gösterilmektedir `trustInfo` FullTrust güvenlik bölgesinde varsayılan izinler için öğesi.  
  
```  
<trustInfo>  
  <security>  
    <applicationRequestMinimum>  
      <PermissionSet ID="FullTrust" Unrestricted="true" />  
      <defaultAssemblyRequest permissionSetReference="FullTrust" />  
    </applicationRequestMinimum>  
  </security>  
</trustInfo>  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Güvenilir Uygulama dağıtımına genel bakış](../deployment/trusted-application-deployment-overview.md)   
 [ClickOnce Uygulama bildirimi](../deployment/clickonce-application-manifest.md)