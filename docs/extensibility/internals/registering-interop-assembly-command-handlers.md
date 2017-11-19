---
title: "Birlikte çalışma derlemesi komut işleyicileri kaydetme | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- interop assemblies, command handlers
- command handling with interop assemblies, registering
ms.assetid: 303cd399-e29d-4ea1-8abe-5e0b59c12a0c
caps.latest.revision: "19"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 6f359c8bcad7bdc32b481fa6fc30a96a8669129f
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="registering-interop-assembly-command-handlers"></a>Birlikte çalışma derlemesi komut işleyicileri kaydetme
Bir VSPackage ile kaydetmeniz gerekir [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] böylece tümleşik geliştirme ortamı (IDE) kendi komutları düzgün şekilde yönlendirir.  
  
 Kayıt, el ile düzenleme veya bir kayıt (.rgs) dosyası kullanarak güncelleştirilebilir. Daha fazla bilgi için bkz: [oluşturma Kaydedici betikleri](/cpp/atl/creating-registrar-scripts).  
  
 Yönetilen paket Framework (MPF) aracılığıyla bu işlevselliği sağlayan <xref:Microsoft.VisualStudio.Shell.ProvideMenuResourceAttribute> sınıfı.  
  
 [Komut tablo biçimi başvurusu](http://msdn.microsoft.com/en-us/09e9c6ef-9863-48de-9483-d45b7b7c798f) kaynakları yönetilmeyen uydu UI DLL'ler bulunur.  
  
## <a name="command-handler-registration-of-a-vspackage"></a>Bir VSPackage komut işleyici kaydı  
 Kullanıcı Arabirimi (UI) için bir işleyici olarak davranan bir VSPackage-tabanlı komutlar gerektirir sonra VSPackage adlı bir kayıt defteri girdisi `GUID`. Bu kayıt defteri girdisi VSPackage'nın UI kaynak dosyası ve bu dosyanın içindeki menüsü kaynak konumunu belirtir. Kayıt defteri girdisini HKEY_LOCAL_MACHINE\Software\Microsoft\VisualStudio altında bulunan\\*\<sürüm >*\Menus, burada  *\<sürüm >* sürümü [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)], örneğin 9.0.  
  
> [!NOTE]
>  HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\VisualStudio kök yolunu\\*\<sürüm >* alternatif ile geçersiz kılınabilir ne zaman kök [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] Kabuk başlatılır. Kök yolu hakkında daha fazla bilgi için bkz: [yükleme VSPackages ile Windows Installer](../../extensibility/internals/installing-vspackages-with-windows-installer.md).  
  
### <a name="the-ctmenu-resource-registry-entry"></a>CTMENU kaynak kayıt defteri girdisi  
 Kayıt defteri girdisini yapıdır:  
  
```  
HKEY_LOCAL_MACHINE\Software\VisualStudio\<Version>\  
  Menus\  
    <GUID> = <Resource Information>  
```  
  
 \<*GUID*> olan `GUID` {XXXXXX-XXXX-XXXX-XXXX-XXXXXXXXX} biçiminde VSPackage biri.  
  
 *\<Kaynak bilgileri >* virgülle ayırarak üç öğe oluşur. Bu öğeler, sırasıyla şunlardır:  
  
 \<*Kaynak DLL yolu*>, \< *menüsü kaynak kimliği*>, \< *menü sürümü*>  
  
 Aşağıdaki tabloda alanlarını açıklayan \< *kaynak bilgileri*>.  
  
|Öğe|Açıklama|  
|-------------|-----------------|  
|\<*Kaynak DLL yolu*>|Bu kaynak menü kaynağı içeren DLL tam yolunu veya bu VSPackage'nın kaynak kullanılacak DLL olduğunu belirten boş bırakılır (, VSPackage kayıtlı paketlerin alt anahtarda belirtildiği gibi).<br /><br /> Bu alanı boş bırakın uygulamadır.|  
|\<*Menü kaynak kimliği*>|Bu kaynak kimliğidir `CTMENU` tüm kullanıcı Arabirimi öğeleri için VSPackage gelen derlenmiş gibi içeren kaynak bir [.vsct](../../extensibility/internals/visual-studio-command-table-dot-vsct-files.md) dosya.|  
|\<*Menü sürümü*>|Bu sürüm için olarak kullanılan bir sayıdır `CTMENU` kaynak. [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)]içeriğini remerge gerekip gerekmediğini belirlemek için bu değeri kullanır `CTMENU` önbelleğinde tüm kaynakla `CTMENU` kaynakları. Bir remerge devenv Kurulum komutu yürüterek tetiklenir.<br /><br /> Bu değer başlangıçta 1 olarak ayarlayın ve gerekir her değişiklikten sonra artar `CTMENU` kaynak ve remerge oluşmadan önce.|  
  
### <a name="example"></a>Örnek  
 Kaynak girişleri birkaç örneği aşağıda verilmiştir:  
  
```  
HKEY_LOCAL_MACHINE\Software\VisualStudio\9.0Exp\  
  Menus\  
    {019971D6-4685-11D2-B48A-0000F87572EB} = ,1, 10  
    {1b027a40-8f43-11d0-8d11-00a0c91bc942} = , 10211, 3  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Kullanıcı arabirimi öğeleri VSPackages nasıl eklenir](../../extensibility/internals/how-vspackages-add-user-interface-elements.md)   
 [Komutlar ve birlikte çalışma derlemeleri kullanma menüleri](../../extensibility/internals/commands-and-menus-that-use-interop-assemblies.md)