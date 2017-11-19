---
title: Proje Modelleme | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- automation [Visual Studio SDK], implementing project objects
- project models, automation
ms.assetid: c8db8fdb-88c1-4b12-86fe-f3c30a18f9ee
caps.latest.revision: "9"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: d654669ad35ce77d840f4852ceb7a6605a8221be
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="project-modeling"></a>Proje Modelleme
Projenizi standart proje nesneleri uygulamak için Otomasyon sağlayan bir sonraki adım: <xref:EnvDTE.Projects> ve `ProjectItems` koleksiyonları; `Project` ve <xref:EnvDTE.ProjectItem> ; ve uygulamanız için benzersiz kalan nesneleri. Bu standart nesneleri Dteinternal.h dosyasında tanımlanır. Standart nesneleri uygulaması BscPrj örnekte sağlanır. Bu sınıfların modelleri olarak yan yana göze kendi standart proje nesneleri oluşturmak için kullanabileceğiniz diğer proje türleri proje nesneleri ile.  
  
 Çağrı yapabilmek için bir Otomasyon tüketici varsayar <xref:EnvDTE.Solution>("`<UniqueProjName>")` ve <xref:EnvDTE.ProjectItems> (`n`) n, çözümdeki belirli bir proje alma dizin numarası. Bu Otomasyon araması yapmadan neden çağırmak ortam <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIHierarchy.GetProperty%2A> VSITEMID_ROOT VSHPROPID_ExtObject VSHPROPID parametre olarak ve ItemId parametre olarak geçirme uygun proje hiyerarşisi üzerinde. `IVsHierarchy::GetProperty`döndüren bir `IDispatch` çekirdek sağlayarak Otomasyon nesnesine işaretçi `Project` uyguladıysanız arabirimi.  
  
 Söz dizimi aşağıdaki gibidir `IVsHierarchy::GetProperty`.  
  
 `HRESULT GetProperty (`  
  
 `VSITEMID` `itemid`,  
  
 `VSHPROPID` `propid`,  
  
 `VARIANT``*pvar`  
  
 `);`  
  
 Projeleri iç içe geçme uyum ve proje öğesi grupları oluşturmak için koleksiyonları kullanın. Hiyerarşi şöyle görünür.  
  
```  
Projects  
  |- Project  
      |- ProjectItems (a collection of ProjectItem)  
          |- ProjectItem (single object) or ProjectItems (another collection)  
```  
  
 İç içe geçme anlamına gelir bir <xref:EnvDTE.ProjectItem> nesne olabilir <xref:EnvDTE.ProjectItems> aynı zamanda koleksiyon için bir `ProjectItems` koleksiyonu, iç içe nesneleri içerebilir. Temel Proje örnek bu iç içe geçme gösterilmemiştir. Uygulama tarafından `Project` nesne genel otomasyon modeli tasarım belirtir ağaç benzeri yapısında katılın.  
  
 Aşağıdaki diyagramda yolunda Proje Otomasyonu izler.  
  
 ![Visual Studio Proje nesneleri](../../extensibility/internals/media/projectobjects.gif "ProjectObjects")  
Proje Otomasyonu  
  
 Uygulamaz varsa bir `Project` nesne ortamına hala genel dönün `Project` yalnızca projenin adını içeren nesne.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 <xref:EnvDTE.Projects>   
 <xref:EnvDTE.ProjectItem>   
 <xref:EnvDTE.ProjectItems>