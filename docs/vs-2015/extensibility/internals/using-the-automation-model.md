---
title: Otomasyon modelini kullanma | Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- automation [Visual Studio SDK], automation model
ms.assetid: 0c7f7889-fbfb-4b19-804f-b742138baecd
caps.latest.revision: 16
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: da79ac654f37b8f9fd9ceaa1eac3df09204f7196
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42695987"
---
# <a name="using-the-automation-model"></a>Otomasyon Modelini Kullanma
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [Otomasyon modelini kullanarak](https://docs.microsoft.com/visualstudio/extensibility/internals/using-the-automation-model).  
  
Otomasyon ile VSPackage'ı bağladıktan sonra özellikleri ve yöntemleri çağırarak elde edebileceğiniz <xref:EnvDTE.DTEClass.GetObject%2A> metodunda <xref:EnvDTE._DTE> nesne, almak istediğiniz nesnesini temsil eden bir dizeye geçiliyor.  
  
## <a name="obtaining-project-objects"></a>Proje nesnelerini alma  
 Bir Otomasyon Tüketici Proje Otomasyon nesneleri nasıl alacağını gösteren iki kod örneği aşağıda verilmiştir. DTE nesnesini alma hakkında daha fazla bilgi için bkz: [nasıl yapılır: DTE ve DTE2 nesnelerine başvurular alma](http://msdn.microsoft.com/library/c92e3c8e-82e6-4a67-85da-e43c50ffd8e4).  
  
```vb  
Sub DoAutomation()  
    Dim MyProjects As Projects  
    MyProjects = DTE.GetObject("AcmeProject")  
End Sub  
```  
  
```cpp#  
void DoAutomation(void)  
{  
  CComQIPtr<Projects> pMyPkg; // Use an IDispatch-derived object type.  
    pMyPkg = pDTE->GetObject("AcmeProjects");   
  
   // The '=' performs a Query Interface.  
   // Assumes pDTE is already available as a global.  
   // Use pMyPkg to access your projects object's properties and methods.  
}  
  
```  
  
 Bu noktada, hiyerarşi modeli taşımak için belirli bir VSPackage parçası olan standart proje nesneleri kullanabilirsiniz.  
  
 Aşağıdaki kod örneği, bir özel proje türünde bir özellik olan özel bir nesne almak gösterilmektedir.:  
  
```vb  
Dim MyPrj As Project  
Dim MyPrjItem As ProjectItem  
Dim objMyObject as MyExtendedObject  
  
MyPrj = MyProjects.Item(1) 'use the Projects collection to get a project  
objMyObject = MyPrj.Object 'You call .Object to get to special Project  
                           'implementation  
objMyObject.MySpecialMethodOrProperty  
```  
  
 Aşağıdaki kod tüm özelliklerin adları listeler [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] ortam **genel** seçeneğini **Araçları** menüsü:  
  
```vb  
dim objDTE  
dim objEnv  
set objDTE = CreateObject("VisualStudio.DTE")  
set objEnv = objDTE.Properties("Environment", "General")  
for each obj in ObjEnv  
MsgBox obj.Name  
Next  
  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 <xref:EnvDTE.DTEClass.GetObject%2A>

