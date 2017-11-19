---
title: "Temel Project nesne modelini genişletme | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- automation object model, extending
- project subtypes, extending automation object model
- automation object model
ms.assetid: 2f95cc53-dff6-476c-bacd-500fb0ff7725
caps.latest.revision: "17"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: b92fe7fece58dd2006507f0285d3c440af437ee4
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="extending-the-object-model-of-the-base-project"></a>Temel Project nesne modelini genişletme
Proje alt aşağıdaki yerlerde temel proje Otomasyon nesne modelini genişletme:  
  
-   Project.Extender ("\<ProjectSubtypeName >")-özel yöntemleri içeren bir nesne sunmak bir proje alt böylece <xref:EnvDTE.Project>. Proje alt kullanıma sunmak için Otomasyon Extender'larının kullanabilirsiniz `Project` nesnesi. <xref:EnvDTE80.IInternalExtenderProvider>Ana proje alt Toplayıcı üzerinde uygulanan arabirimi, nesne için teklif `VSHPROPID_ExtObjectCATID` gelen <xref:Microsoft.VisualStudio.Shell.Interop.__VSSPROPID2> (karşılık gelen bir `itemid` VSITEMID_ROOT, değerini gelen `VSITEMID`) catID.  
  
-   ProjectItem.Extender ("\<ProjectSubtypeName >")-bir nesne belirli özel yöntemleriyle sunmak bir proje alt böylece <xref:EnvDTE.ProjectItem> projedeki nesne. Proje alt Otomasyon Extender'larının bu nesneyi kullanıma sunmak için kullanabilirsiniz. <xref:EnvDTE80.IInternalExtenderProvider> Ana proje alt Toplayıcı üzerinde uygulanan arabirimi gereken alt nesne için sunmak `VSHPROPID_ExtObjectCATID` gelen <xref:Microsoft.VisualStudio.Shell.Interop.__VSHPROPID2> (istenen bir karşılık gelen `VSITEMID`) catID.  
  
-   Project.Properties - Bu koleksiyonun yapılandırma bağımsız özellikleri kullanıma sunan `Project` nesnesi. Proje özellikleri hakkında daha fazla bilgi için bkz: <xref:EnvDTE.Project.Properties%2A>. Proje alt Otomasyon Extender'larının özelliklerini bu koleksiyona eklemek için kullanabilirsiniz. <xref:EnvDTE80.IInternalExtenderProvider> Ana proje alt Toplayıcı üzerinde uygulanan arabirimi gereken alt nesne için sunmak `VSHPROPID_BrowseObjectCATID` VSHPROPID2 gelen (karşılık gelen bir `itemid` VSITEMID_ROOT, değerini gelen <xref:Microsoft.VisualStudio.Shell.Interop.__VSHPROPID2>) catID.  
  
-   Configuration.Properties - Bu koleksiyon proje (örneğin, hata ayıklama) belirli bir yapılandırma için yapılandırma bağımlı özelliklerini gösterir. Daha fazla bilgi için <xref:EnvDTE.Configuration>. Proje alt Otomasyon Extender'larının özelliklerini bu koleksiyona eklemek için kullanabilirsiniz. <xref:EnvDTE80.IInternalExtenderProvider> Ana proje alt Toplayıcı üzerinde uygulanan arabirimi sunar, nesne için catID `VSHPROPID_CfgBrowseObjectCATID` (karşılık gelen bir `itemid` değerini <xref:Microsoft.VisualStudio.VSConstants.VSITEMID_ROOT>). <xref:Microsoft.VisualStudio.Shell.Interop.IVsCfgBrowseObject>Arabirimi bir yapılandırma Gözat nesnesi diğerinden ayırt etmek için kullanılır.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 <xref:Microsoft.VisualStudio.Shell.Interop.__VSFPROPID>