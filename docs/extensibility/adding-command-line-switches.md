---
title: "Komut satırı anahtarları ekleme | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- command-line switches, adding
- command-line switches, retrieving
- IVsAppCommandLine::GetOption method
- command line, switches
ms.assetid: 8bbbd87e-76fe-4fb5-8ef9-65f5e31967cf
caps.latest.revision: "21"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: d686e7b68e790c419679bf495bf08ad4cd4807e2
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="adding-command-line-switches"></a>Komut satırı anahtarları ekleme
Devenv.exe yürütüldüğünde, VSPackage uygulama komut satırı anahtarları ekleyebilirsiniz. Kullanım <xref:Microsoft.VisualStudio.Shell.ProvideAppCommandLineAttribute> adını anahtar ve özelliklerini bildirmek için. Bu örnekte, MySwitch anahtar adlı VSPackage öğesinin bir alt kümesi için eklenen **AddCommandSwitchPackage** bağımsız değişken içermeyen ve otomatik olarak yüklenen VSPackage ile.  
  
```csharp  
[ProvideAppCommandLine("MySwitch", typeof(AddCommandSwitchPackage), Arguments = "0", DemandLoad = 1)]  
```  
  
 Adlandırılmış parametreler aşağıdaki tabloda gösterilmiştir  
  
 Arguments  
 Anahtar için bağımsız değişken sayısı. Olabilir "*", veya bir bağımsız değişkenleri listesi.  
  
 DemandLoad  
 Bu 1, aksi halde 0 olarak ayarlamak üzere ayarlanmışsa VSPackage otomatik olarak yükleyin.  
  
 HelpString  
 Görüntülemek için Yardım dize veya kaynak kimliği dizesi **devenv /?**.  
  
 Ad  
 Anahtar.  
  
 PackageGuid  
 Paket GUID'si.  
  
 İlk bağımsız değişkenler genellikle 0 veya 1 değeri. Özel bir değeri ' *' tüm kalanı komut satırı bağımsız değişkeni olduğunu göstermek için kullanılır. Bu, bir kullanıcı bir hata ayıklayıcı komut dizesinde burada geçmelidir senaryoları hata ayıklama için yararlı olabilir.  
  
 DemandLoad ya da değerdir `true` (1) veya `false` (0) VSPackage otomatik olarak yüklenmesi gerektiğini belirtir.  
  
 HelpString değeri devenv görünen dize kaynak kimliğidir /? Yardım görüntüleme. Bu değer "nnn bir tamsayı olduğu #nnn" biçiminde olmalıdır. Kaynak dosyasında dize değeri bir yeni satır karakteri bitmelidir.  
  
 Ad değer anahtar adıdır.  
  
 Bu anahtar uygulayan paket GUID'i PackageGuid değerdir. IDE komut satırı anahtarını uygulandığı kayıt defterinde VSPackage bulmak için bu GUID'i kullanır.  
  
## <a name="retrieving-command-line-switches"></a>Komut satırı anahtarları alma  
 Paketinizi yüklendiğinde, aşağıdaki adımları izleyerek komut satırı anahtarları alabilir.  
  
1.  VSPackage's içinde <xref:Microsoft.VisualStudio.Shell.Interop.IVsPackage.SetSite%2A> uygulaması, çağrı `QueryService` üzerinde <xref:Microsoft.VisualStudio.Shell.Interop.SVsAppCommandLine> almak için <xref:Microsoft.VisualStudio.Shell.Interop.IVsAppCommandLine> arabirimi.  
  
2.  Çağrı <xref:Microsoft.VisualStudio.Shell.Interop.IVsAppCommandLine.GetOption%2A> kullanıcı girilen komut satırı anahtarları alınamadı.  
  
 Aşağıdaki kod, MySwitch komut satırı anahtarını olup kullanıcı tarafından girilen çıkışı bulmak gösterilmektedir:  
  
```csharp  
IVsAppCommandLine cmdline = (IVsAppCommandLine)GetService(typeof(SVsAppCommandLine));  
  
int isPresent = 0;  
string optionValue = "";  
  
cmdline.GetOption("MySwitch", out isPresent, out optionValue);  
```  
  
 Bu, paket yüklendiği her durumda, komut satırı anahtarları denetlemek için sorumluluğundadır.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsAppCommandLine>   
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsPackage.SetSite%2A>   
 [Devenv komut satırı anahtarları](../ide/reference/devenv-command-line-switches.md)   
 [CreatePkgDef yardımcı programı](../extensibility/internals/createpkgdef-utility.md)   
 [. Pkgdef dosyaları](../extensibility/modifying-the-isolated-shell-by-using-the-dot-pkgdef-file.md)