---
title: FileClassifier görevi | Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords:
- classifying a resource set to embed in an assembly [WPF MSBuild]
- non-localizable resources [WPF MSBuild], classifying to embed in an assembly
- FileClassifier task [WPF MSBuild]
ms.assetid: 14e03310-fcc0-4bb2-a84d-cda12be66367
caps.latest.revision: 10
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 06decaf5a2a59b4efb2e4f30f41298ebd3e5d533
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42687564"
---
# <a name="fileclassifier-task"></a>FileClassifier Görevi
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [FileClassifier görevi](https://docs.microsoft.com/visualstudio/msbuild/fileclassifier-task).  
  
  
<xref:Microsoft.Build.Tasks.Windows.FileClassifier> Görev bir bütünleştirilmiş kod içine katıştırılmış olarak kaynak kaynak kümesini sınıflandırır. Bir kaynak yerelleştirilebilir değil ise, ana uygulama derlemesine eklenir; Aksi takdirde, bir uydu derlemeye eklenir.  
  
## <a name="task-parameters"></a>Görev parametreleri  
  
|Parametre|Açıklama|  
|---------------|-----------------|  
|`CLREmbeddedResource`|Kullanılmayan.|  
|`CLRResourceFiles`|Kullanılmayan.|  
|`CLRSatelliteEmbeddedResource`|Kullanılmayan.|  
|`Culture`|İsteğe bağlı **dize** parametresi.<br /><br /> Derleme için kullanılacak kültürü belirtir. Bu değer **null** derleme yerelleştirilemeyen ise. Varsa **null**, küçük değer varsayılan değerdir **CultureInfo.InvariantCulture** döndürür.|  
|`MainEmbeddedFiles`|İsteğe bağlı **Itaskıtem []** çıkış parametresi.<br /><br /> Ana derleme gömülü yerelleştirilemeyen kaynaklar belirtir.|  
|`OutputType`|Gerekli **dize** parametresi.<br /><br /> Belirtilen kaynak dosyalarıyla katıştırmak için dosya türünü belirtir. Geçerli değerler **exe**, **winexe**, veya **Kitaplığı**.|  
|`SatelliteEmbeddedFiles`|İsteğe bağlı **Itaskıtem []** çıkış parametresi.<br /><br /> Belirtilen kültür için uydu derlemesine gömülür yerelleştirilebilir dosyaları belirtir **kültür** parametresi.|  
|`SourceFiles`|Gerekli **Itaskıtem []** parametresi.<br /><br /> Dosyaları sınıflandırmak için listesini belirtir.|  
  
## <a name="remarks"></a>Açıklamalar  
 Varsa **kültür** parametresi ayarlanmadı, kullanılarak belirtilen tüm kaynakların **Kaynakdosyalar** parametresi yerelleştirilemeyen; bir ileilişkiliolduklarısüreceAksitakdirde,bunlaryerelleştirilebilir **Yerelleştirilebilir** ayarlanan öznitelik **false**.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek, tek bir kaynak dosyasını kaynak olarak sınıflandırır ve French-Canadian (fr-CA) kültür için bir uydu derlemeye katıştırır.  
  
```  
<Project xmlns="http://schemas.microsoft.com/developer/msbuild/2003">  
  <UsingTask  
    TaskName="Microsoft.Build.Tasks.Windows.FileClassifier"   
    AssemblyFile="C:\Program Files\Reference Assemblies\Microsoft\Framework\v3.0\PresentationBuildTasks.dll" />  
  <ItemGroup>  
    <Resource Include="Resource1.bmp" />  
  </ItemGroup>  
  <Target Name="FileClassifierTask">  
    <FileClassifier  
      SourceFiles="Resource1.bmp"  
      Culture="fr-CA"  
      OutputType="exe" />  
  </Target>  
</Project>  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [WPF MSBuild başvurusu](../msbuild/wpf-msbuild-reference.md)   
 [Görev başvurusu](../msbuild/wpf-msbuild-task-reference.md)   
 [MSBuild başvurusu](../msbuild/msbuild-reference.md)   
 [Görev başvurusu](../msbuild/msbuild-task-reference.md)   
 [WPF uygulaması (WPF) oluşturma](http://msdn.microsoft.com/library/a58696fd-bdad-4b55-9759-136dfdf8b91c)



