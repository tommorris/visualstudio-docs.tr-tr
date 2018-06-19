---
title: 'Nasıl yapılır: görevlerdeki hataları yoksayma | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology: msbuild - "vs-ide-sdk"
ms.topic: conceptual
helpviewer_keywords:
- MSBuild, ignoring errors
- ContinueOnError attribute [MSBuild]
ms.assetid: e2f1ca4f-787b-44bd-bc64-81a036025e96
author: mikejo5000
ms.author: mikejo
manager: douge
ms.openlocfilehash: 348a026815d0d48390fed5741e6dba741fda9937
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/19/2018
ms.locfileid: "31578607"
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