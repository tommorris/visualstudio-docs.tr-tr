---
title: "Yürütme görevi | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: http://schemas.microsoft.com/developer/msbuild/2003#Exec
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords:
- Exec task [MSBuild]
- MSBuild, Exec task
ms.assetid: c9b7525a-b1c9-40fc-8bce-77a5b8f960d8
caps.latest.revision: "20"
author: kempb
ms.author: kempb
manager: ghogen
ms.openlocfilehash: 7447f3f6fc9042bbcca5fc176e26200f4848a04c
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="exec-task"></a>Yürütme Görevi
Belirtilen program veya komut belirtilen bağımsız değişkenler kullanılarak çalıştırılır.  
  
## <a name="parameters"></a>Parametreler  
 Aşağıdaki tabloda parametrelerini açıklar `Exec` görev.  
  
|Parametre|Açıklama|  
|---------------|-----------------|  
|`Command`|Gerekli `String` parametresi.<br /><br /> Çalıştırmak için komutu. Bunlar attrib gibi sistem komutlarını veya program.exe, runprogram.bat veya setup.msi gibi bir yürütülebilir dosya olabilir.<br /><br /> Bu parametre, komutları birden fazla satır içerebilir. Alternatif olarak, birden çok komutları bir toplu iş dosyasında koy ve, bu parametre kullanarak çalıştırın.|  
|`CustomErrorRegularExpression`|İsteğe bağlı `String` parametresi.<br /><br /> Nokta hata satırlarını aracı çıkışı için kullanılan normal bir ifade belirtir. Bu, genellikle biçimlendirilmiş bir çıktı oluşturmak için araçları yararlıdır.|  
|`CustomWarningRegularExpression`|İsteğe bağlı `String` parametresi.<br /><br /> Araç çıktısını nokta uyarı satırlarında için kullanılan normal bir ifade belirtir. Bu, genellikle biçimlendirilmiş bir çıktı oluşturmak için araçları yararlıdır.|  
|`ExitCode`|İsteğe bağlı `Int32` çıkış parametresi salt okunur.<br /><br /> Yürütülen komutun tarafından sağlanan çıkış kodu belirtir.|  
|`IgnoreExitCode`|İsteğe bağlı `Boolean` parametresi.<br /><br /> Varsa `true`, görev tarafından yürütülen komutu sağlanan çıkış kodu yok sayar. Aksi halde, görev döndürür `false` yürütülen komutu sıfır olmayan çıkış kodu döndürmesi durumunda.|  
|`IgnoreStandardErrorWarningFormat`|İsteğe bağlı `Boolean` parametresi.<br /><br /> Varsa `false`, standart hata/uyarı biçim ile eşleşmesi çıktıda satırları seçer ve hatalar/uyarılar kaydeder. Varsa `true`, bu davranışı devre dışı. Varsayılan değer `false` şeklindedir.|  
|`Outputs`|İsteğe bağlı <xref:Microsoft.Build.Framework.ITaskItem> `[]` çıkış parametresi.<br /><br /> Görev çıktı öğeleri içerir. `Exec` Görev bu kendisini ayarlamaz. Bunları ayarlarsanız gibi böylece daha sonra projesinde kullanılan bunun yerine, bunları sağlayabilirsiniz.|  
|`StdErrEncoding`|İsteğe bağlı `String` çıkış parametresi.<br /><br /> Yakalanan görev standart hata akışı kodlamasını belirtir. Geçerli varsayılandır konsol çıkış kodlama.|  
|`StdOutEncoding`|İsteğe bağlı `String` çıkış parametresi.<br /><br /> Yakalanan görev standart çıktı akışı kodlamasını belirtir. Geçerli varsayılandır konsol çıkış kodlama.|  
|`WorkingDirectory`|İsteğe bağlı `String` parametresi.<br /><br /> Komutun çalıştırılacağı dizini belirtir.|  
  
## <a name="remarks"></a>Açıklamalar  
 Bu görevin belirli bir zaman yararlıdır [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] görevi gerçekleştirmek istediğiniz işlemi kullanılabilir değil. Ancak, `Exec` daha belirli bir görevi aksine görev aracından çıktıyı toplayabilir veya, çalıştığını komutu.  
  
 `Exec` Görev doğrudan bir işlem çağırma yerine cmd.exe çağırır.  
  
 Bu belgede listelenen parametreleri ek olarak, bu görev parametrelerinden devralır <xref:Microsoft.Build.Tasks.ToolTaskExtension> sınıfı, kendisi <xref:Microsoft.Build.Utilities.ToolTask> sınıfı. Bu ek parametreler ve açıklamalarının listesi için bkz: [ToolTaskExtension taban sınıfı](../msbuild/tooltaskextension-base-class.md).  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek kullanır `Exec` bir komut çalıştırmak için görev.  
  
```xml  
<Project xmlns="http://schemas.microsoft.com/developer/msbuild/2003">  
    <ItemGroup>  
        <Binaries Include="*.dll;*.exe"/>  
    </ItemGroup>  
  
    <Target Name="SetACL">  
        <!-- set security on binaries-->  
        <Exec Command="echo y| cacls %(Binaries.Identity) /G everyone:R"/>  
    </Target>  
  
</Project>  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Görevler](../msbuild/msbuild-tasks.md)   
 [Görev başvurusu](../msbuild/msbuild-task-reference.md)
