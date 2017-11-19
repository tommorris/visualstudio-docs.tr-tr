---
title: "Nasıl yapılır: görevlerdeki hataları yoksayma | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- MSBuild, ignoring errors
- ContinueOnError attribute [MSBuild]
ms.assetid: e2f1ca4f-787b-44bd-bc64-81a036025e96
caps.latest.revision: "18"
author: kempb
ms.author: kempb
manager: ghogen
ms.openlocfilehash: 6fbdf661b49fb60ec6b1e18c6886b9bdcc946437
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="how-to-ignore-errors-in-tasks"></a>Nasıl Yapılır: Görevlerdeki Hataları Yoksayma
Bazen bir yapı hatalarının bazı görevler dayanıklı olmasını istiyorsunuz. Bu kritik olmayan görevleri başarısız olursa, yapı hala gerekli çıkış üretebilir çünkü devam etmek istiyorsunuz. Örneğin, bir proje kullanıyorsa, bir `SendMail` her bileşenin oluşturulduktan sonra bir e-posta iletisi göndermek için görev posta sunucuları kullanılamıyor ve durum iletileri gönderilemez bile tamamlanıncaya kadar devam etmek derleme için kabul edilebilir düşünebilirsiniz. Veya Ara dosyaları genellikle derleme sırasında silinirse, örneğin, bu dosyaları bile silinemez zaman tamamlanıncaya kadar devam etmek derleme için kabul edilebilir düşünebilirsiniz.  
  
## <a name="using-the-continueonerror-attribute"></a>ContinueOnError özniteliği kullanma  
 `ContinueOnError` Özniteliği `Task` öğesi denetleyen bir yapı durdurur veya bir görev başarısız olduğunda devam eder. Bu öznitelik, ayrıca yapı devam ettiğinde hataları hata veya uyarı kabul edilip edilmeyeceğini denetler.  
  
 `ContinueOnError` Özniteliği aşağıdaki değerlerden birini içerebilir:  
  
-   **WarnAndContinue** veya **doğru**. Bir görev başarısız olduğunda, sonraki görevlerinde [hedef](../msbuild/target-element-msbuild.md) öğesi ve yapı devam yürütmek ve görevin tüm hataları, uyarıları olarak kabul edilir.  
  
-   **ErrorAndContinue**. Bir görev başarısız olduğunda, sonraki görevlerinde `Target` öğesi ve yapı devam yürütmek ve görevin tüm hataları hata olarak kabul edilir.  
  
-   **ErrorAndStop** veya **false** (varsayılan). Bir görev başarısız olursa, kalan görevlere `Target` öğesi ve yapı olmayan yürütülen ve tüm `Target` öğesi ve yapı olarak kabul başarısız oldu.  
  
 Yalnızca desteklenen 4.5 önce .NET Framework sürümleri `true` ve `false` değerleri.  
  
 Varsayılan değer olan `ContinueOnError` olan `ErrorAndStop`. Öznitelik ayarlanırsa, `ErrorAndStop`, davranışı açık proje dosyasını okur herkes için yaptığınız.  
  
#### <a name="to-ignore-an-error-in-a-task"></a>Bir görevde bir hatayı yok saymayı  
  
-   Kullanım `ContinueOnError` görev özniteliği. Örneğin:  
  
     `<Delete Files="@(Files)" ContinueOnError="WarnAndContinue"/>`  
  
## <a name="example"></a>Örnek  
 Aşağıdaki kod örneği gösterilmektedir `Build` hedef hala çalışır ve yapı kabul edilen başarılı, bile `Delete` görev başarısız olur.  
  
```xml  
<Project DefaultTargets="FakeBuild"  
    xmlns="http://schemas.microsoft.com/developer/msbuild/2003">  
    <ItemGroup>  
        <Files Include="*.obj"/>  
    </ItemGroup>  
    <Target Name="Clean">  
        <Delete Files="@(Files)" ContinueOnError="WarnAndContinue"/>  
    </Target>  
  
    <Target Name="FakeBuild" DependsOnTargets="Clean">  
        <Message Text="Building after cleaning..."/>  
    </Target>  
</Project>  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.
[MSBuild](../msbuild/msbuild.md)  
 [Görev başvurusu](../msbuild/msbuild-task-reference.md)   
 [Görevler](../msbuild/msbuild-tasks.md)