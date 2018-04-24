---
title: UsingTask öğesi (MSBuild) | Microsoft Docs
ms.custom: ''
ms.date: 03/13/2017
ms.technology: msbuild
ms.topic: reference
f1_keywords:
- http://schemas.microsoft.com/developer/msbuild/2003#UsingTask
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords:
- UsingTask element [MSBuild]
- <UsingTask> element [MSBuild]
ms.assetid: 20247902-9446-4a1f-8253-5c7a17e4fe43
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: f95e09639e9236b64f9c18c9bd90e6850ee13d86
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/19/2018
---
# <a name="usingtask-element-msbuild"></a>UsingTask Öğesi (MSBuild)
Başvuru görev eşleyen bir [görev](../msbuild/task-element-msbuild.md) görev uygulamasını içeren derlemenin öğesi.  

 \<Proje >  
 \<UsingTask >  

## <a name="syntax"></a>Sözdizimi  

```  
<UsingTask TaskName="TaskName"  
    AssemblyName = "AssemblyName"   
    TaskFactory = "ClassName"  
    Condition="'String A'=='String B'" />  
```  

## <a name="attributes-and-elements"></a>Öznitelikler ve Öğeler  
 Öznitelikler, alt ve üst öğeler aşağıdaki bölümlerde açıklanmaktadır.  

### <a name="attributes"></a>Öznitelikler  

|Öznitelik|Açıklama|  
|---------------|-----------------|  
|`AssemblyName`|Her iki `AssemblyName` özniteliği veya `AssemblyFile` özniteliği gereklidir.<br /><br /> Yüklenecek derlemenin adı. `AssemblyName` Özniteliği güçlü adlandırma gerekli olmamasına rağmen tanımlayıcı adlı derlemeler kabul eder. Bu öznitelik kullanarak eşdeğerdir kullanarak bir derlemeyi yüklemeye <xref:System.Reflection.Assembly.Load%2A> .NET yöntemi.<br /><br /> Bu öznitelik, kullanamazsınız `AssemblyFile` özniteliği kullanılır.|  
|`AssemblyFile`|Ya da `AssemblyName` veya `AssemblyFile` özniteliği gereklidir.<br /><br /> Derlemenin dosya yolu. Bu öznitelik tam yol veya göreli yollar kabul eder. Göreli yollardır proje dosyası veya hedefleri dosyasının dizin göreli nerede `UsingTask` öğesi bildirildi. Bu öznitelik kullanarak eşdeğerdir kullanarak bir derlemeyi yüklemeye <xref:System.Reflection.Assembly.LoadFrom%2A> .NET yöntemi.<br /><br /> Bu öznitelik, kullanamazsınız `AssemblyName` özniteliği kullanılır.|  
|`TaskFactory`|İsteğe bağlı öznitelik.<br /><br /> Belirtilen örneğini oluşturmaktan sorumlu derlemesindeki sınıfını belirtir `Task` adı.  Kullanıcı ayrıca belirtebilir bir `TaskBody` görev üreteci alır ve görev oluşturmak için kullandığı bir alt öğesi olarak. İçeriğini `TaskBody` görev Fabrika özeldir.|  
|`TaskName`|Gerekli öznitelik.<br /><br /> Bir derlemeye ait başvurmak için görev adı. Belirsizlikleri olası varsa, bu öznitelik her zaman tam ad belirtmelisiniz. MSBuild belirsizlikleri varsa, beklenmeyen sonuçlara neden rasgele bir eşleşme seçer.|  
|`Condition`|İsteğe bağlı öznitelik.<br /><br /> Değerlendirilecek koşulu. Daha fazla bilgi için bkz: [koşullar](../msbuild/msbuild-conditions.md).|  

### <a name="child-elements"></a>Alt Öğeler  

|Öğe|Açıklama|  
|-------------|-----------------|  
|[ParameterGroup](../msbuild/parametergroup-element.md)|Oluşturulan görevi görünen parametre kümesi belirtilen tarafından `TaskFactory`.|  
|[Görev](../msbuild/task-element-msbuild.md)|Geçirilen verileri `TaskFactory` bir görev örneği.|  

### <a name="parent-elements"></a>Üst Öğeler  

|Öğe|Açıklama|  
|-------------|-----------------|  
|[Project](../msbuild/project-element-msbuild.md)|Gerekli kök öğesinin bir [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] proje dosyası.|  

## <a name="remarks"></a>Açıklamalar  
 Ortam değişkenleri, komut satırı özellikleri ve proje düzeyi özellikleri de herhangi bir yere başvurulabilir `UsingTask` açıkça veya alınan proje dosyası aracılığıyla proje dosyasında görünürse öğesi. Daha fazla bilgi için bkz: [görevleri](../msbuild/msbuild-tasks.md).  

> [!NOTE]
>  Proje düzeyi özellikleri varsa hiçbir anlamı `UsingTask` öğesi genel olarak MSBuild altyapısı ile kayıtlı .tasks dosyaları birinden geliyor. Proje düzeyi özellikleri MSBuild için genel değil.  

 MSBuild 4. 0'da, görevler kullanma .overridetask dosyalarından yüklenebilir.  

## <a name="example"></a>Örnek  
 Aşağıdaki örnekte nasıl kullanılacağını gösterir `UsingTask` öğesi ile bir `AssemblyName` özniteliği.  

```xml  
<UsingTask TaskName="MyTask" AssemblyName="My.Assembly" TaskFactory="MyTaskFactory">  
       <ParameterGroup>  
              <Parameter1 ParameterType="System.String" Required="False" Output="False"/>  
              <Parameter2 ParameterType="System.Int" Required="True" Output="False"/>  
              ...  
</ParameterGroup>  
       <TaskBody>  
      ... Task factory-specific data ...  
       </TaskBody>  
</UsingTask>  
```  

## <a name="example"></a>Örnek  
 Aşağıdaki örnekte nasıl kullanılacağını gösterir `UsingTask` öğesi ile bir `AssemblyFile` özniteliği.  

```xml  
<UsingTask TaskName="Email"  
              AssemblyFile="c:\myTasks\myTask.dll" />  
```  

## <a name="see-also"></a>Ayrıca Bkz.  
 [Görevler](../msbuild/msbuild-tasks.md)   
 [Görev başvurusu](../msbuild/msbuild-task-reference.md)   
 [Proje dosyası şema başvurusu](../msbuild/msbuild-project-file-schema-reference.md)
