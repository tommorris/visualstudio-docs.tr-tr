---
title: "Kaydetme ve kaydını VSPackages | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- registration, VSPackages
- VSPackages, registering
ms.assetid: e25e7a46-6a55-4726-8def-ca316f553d6b
caps.latest.revision: "35"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 4443195babbe3f8926633a992aa942dcb80dc3f3
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="registering-and-unregistering-vspackages"></a>Kaydetme ve kaydını kaldırma VSPackages
Bir VSPackage kaydetmek için öznitelikler kullanın, ancak  
  
## <a name="registering-a-vspackage"></a>Bir VSPackage kaydetme  
 Yönetilen VSPackages kaydını denetlemek için öznitelikler kullanabilirsiniz. Tüm kayıt bilgileri .pkgdef dosyasında yer alır. Dosya tabanlı kayıt hakkında daha fazla bilgi için bkz: [CreatePkgDef yardımcı programı](../extensibility/internals/createpkgdef-utility.md).  
  
 Aşağıdaki kod standart kayıt öznitelikleri, VSPackage kaydetmek için nasıl kullanılacağını gösterir.  
  
```csharp  
[PackageRegistration(UseManagedResourcesOnly = true)]  
[Guid("0B81D86C-0A85-4f30-9B26-DD2616447F95")]  
public sealed class BasicPackage : Package  
{. . .}  
```  
  
## <a name="unregistering-an-extension"></a>Uzantı kaydı siliniyor  
 Farklı VSPackages çok miktarda denemek ve Deneysel örneğinden kaldırmak istiyorsanız, yalnızca çalıştırabilirsiniz **sıfırlama** komutu. Ara **Visual Studio deneysel örneği sıfırlama** başlangıç sayfasında, bilgisayarınızın veya komut satırından şu komutu çalıştırın:  
  
```vb  
<location of Visual Studio 2015 install>\"Microsoft Visual Studio 14.0\VSSDK\VisualStudioIntegration\Tools\Bin\CreateExpInstance.exe" /Reset /VSInstance=14.0 /RootSuffix=Exp  
```  
  
 Visual Studio, geliştirme örneği üzerinde yüklü olan uzantı kaldırmak istiyorsanız, Git **Araçlar / Uzantılar ve güncelleştirmeler**uzantısını bulun ve tıklatın **kaldırma**.  
  
 Bazı nedenlerden dolayı bu yöntemlerin hiçbiri uzantısını kaldırma sırasında başarılı olursa, komut satırından VSPackage derleme gibi kaydını kaldırabilirsiniz:  
  
```  
<location of Visual Studio 2015 install>\"Microsoft Visual Studio 14.0\VSSDK\VisualStudioIntegration\Tools\Bin\regpkg" /unregister <pathToVSPackage assembly>  
```  
  
<a name="using-a-custom-registration-attribute-to-register-an-extension"></a>  
  
## <a name="use-a-custom-registration-attribute-to-register-an-extension"></a>Uzantı kaydetmek için bir özel kayıt özniteliği kullanın  
  
Belirli durumlarda Uzantınız için yeni bir kayıt öznitelik oluşturmanız gerekebilir. Kayıt öznitelikleri yeni kayıt defteri anahtarlarını eklemek veya mevcut anahtarlarına yeni değerler eklemek için kullanabilirsiniz. Yeni öznitelik öğesinden türetilmelidir <xref:Microsoft.VisualStudio.Shell.RegistrationAttribute>, ve geçersiz kılmanız gerekir <xref:Microsoft.VisualStudio.Shell.RegistrationAttribute.Register%2A> ve <xref:Microsoft.VisualStudio.Shell.RegistrationAttribute.Unregister%2A> yöntemleri.  
  
### <a name="creating-a-custom-attribute"></a>Özel bir öznitelik oluşturma  
  
Aşağıdaki kod, yeni bir kayıt öznitelik oluşturulacağını gösterir.  
  
```csharp  
[AttributeUsage(AttributeTargets.Class, Inherited = true, AllowMultiple = false)]  
    public class CustomRegistrationAttribute : RegistrationAttribute  
    {  
    }  
```  
  
 <xref:System.AttributeUsageAttribute> Öznitelik sınıfları program öğesi (sınıfı, yöntem, vb.), öznitelik ilgilidir, onu birden çok kez kullanılıp kullanılamayacağını ve devralınabilir olup olmadığını belirtmek için kullanılır.  
  
### <a name="creating-a-registry-key"></a>Bir kayıt defteri anahtarı oluşturma  
  
Aşağıdaki kodda özel öznitelik oluşturur bir **özel** kaydedilmekte olan VSPackage anahtarı altında alt anahtar.  
  
```csharp  
public override void Register(RegistrationAttribute.RegistrationContext context)  
{  
    Key packageKey = null;  
    try  
    {   
        packageKey = context.CreateKey(@"Packages\{" + context.ComponentType.GUID + @"}\Custom");  
        packageKey.SetValue("NewCustom", 1);  
    }  
    finally  
    {  
        if (packageKey != null)  
            packageKey.Close();  
    }  
}  
  
public override void Unregister(RegistrationContext context)  
{  
    context.RemoveKey(@"Packages\" + context.ComponentType.GUID + @"}\Custom");  
}  
```  
  
### <a name="creating-a-new-value-under-an-existing-registry-key"></a>Varolan bir kayıt defteri anahtarı altında yeni bir değer oluşturma  
  
Mevcut bir anahtarı için özel değerler ekleyebilirsiniz. Aşağıdaki kod bir VSPackage kayıt anahtarı için yeni bir değer ekleme gösterir.  
  
```csharp  
public override void Register(RegistrationAttribute.RegistrationContext context)  
{  
    Key packageKey = null;  
    try  
    {   
        packageKey = context.CreateKey(@"Packages\{" + context.ComponentType.GUID + "}");  
        packageKey.SetValue("NewCustom", 1);  
    }  
    finally  
    {  
        if (packageKey != null)  
            packageKey.Close();  
                }  
}  
  
public override void Unregister(RegistrationContext context)  
{  
    context.RemoveValue(@"Packages\" + context.ComponentType.GUID, "NewCustom");  
}  
```
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [VSPackages](../extensibility/internals/vspackages.md)