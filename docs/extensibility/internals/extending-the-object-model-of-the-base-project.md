---
title: Temel Project nesne modelini genişletme | Microsoft Docs
ms.date: 03/22/2018
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- automation object model, extending
- project subtypes, extending automation object model
- automation object model
ms.assetid: 2f95cc53-dff6-476c-bacd-500fb0ff7725
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 9cffbecf585f6f8be4174531a91e466f65ab9a72
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="extending-the-object-model-of-the-base-project"></a>Temel Project nesne modelini genişletme

Proje alt aşağıdaki yerlerde temel proje Otomasyon nesne modelini genişletme:

-   Project.Extender ("\<ProjectSubtypeName >")-özel yöntemleri içeren bir nesne sunmak bir proje alt böylece <xref:EnvDTE.Project>. Proje alt kullanıma sunmak için Otomasyon Extender'larının kullanabilirsiniz `Project` nesnesi. <xref:EnvDTE80.IInternalExtenderProvider> Ana proje alt Toplayıcı üzerinde uygulanan arabirimi, nesne için teklif `VSHPROPID_ExtObjectCATID` gelen <xref:Microsoft.VisualStudio.Shell.Interop.__VSSPROPID2> (karşılık gelen bir `itemid` değerini [VSITEMID. Kök](<xref:Microsoft.VisualStudio.VSConstants.VSITEMID#Microsoft_VisualStudio_VSConstants_VSITEMID_Root>)) catID.

-   ProjectItem.Extender ("\<ProjectSubtypeName >")-bir nesne belirli özel yöntemleriyle sunmak bir proje alt böylece <xref:EnvDTE.ProjectItem> projedeki nesne. Proje alt Otomasyon Extender'larının bu nesneyi kullanıma sunmak için kullanabilirsiniz. <xref:EnvDTE80.IInternalExtenderProvider> Ana proje alt Toplayıcı üzerinde uygulanan arabirimi gereken alt nesne için sunmak `VSHPROPID_ExtObjectCATID` gelen <xref:Microsoft.VisualStudio.Shell.Interop.__VSHPROPID2> (istenen bir karşılık gelen <xref:Microsoft.VisualStudio.VSConstants.VSITEMID>) catID.

-   Project.Properties - Bu koleksiyon sunan bağımsız yapılandırma özelliklerini `Project` nesnesi. Proje özellikleri hakkında daha fazla bilgi için bkz: <xref:EnvDTE.Project.Properties%2A>. Proje alt Otomasyon Extender'larının özelliklerini bu koleksiyona eklemek için kullanabilirsiniz. <xref:EnvDTE80.IInternalExtenderProvider> Ana proje alt Toplayıcı üzerinde uygulanan arabirimi gereken alt nesne için sunmak `VSHPROPID_BrowseObjectCATID` VSHPROPID2 gelen (karşılık gelen bir `itemid` değerini [VSITEMID. Kök](<xref:Microsoft.VisualStudio.VSConstants.VSITEMID#Microsoft_VisualStudio_VSConstants_VSITEMID_Root>), gelen <xref:Microsoft.VisualStudio.Shell.Interop.__VSHPROPID2>) catID.

-   Configuration.Properties - Bu koleksiyonu (örneğin, hata ayıklama) belirli bir yapılandırma için proje yapılandırmaya bağlı özelliklerini gösterir. Daha fazla bilgi için bkz. <xref:EnvDTE.Configuration>. Proje alt Otomasyon Extender'larının özelliklerini bu koleksiyona eklemek için kullanabilirsiniz. <xref:EnvDTE80.IInternalExtenderProvider> Ana proje alt Toplayıcı üzerinde uygulanan arabirimi sunar, nesne için catID `VSHPROPID_CfgBrowseObjectCATID` (karşılık gelen bir `itemid` değerini [VSITEMID. Kök](<xref:Microsoft.VisualStudio.VSConstants.VSITEMID#Microsoft_VisualStudio_VSConstants_VSITEMID_Root>)). <xref:Microsoft.VisualStudio.Shell.Interop.IVsCfgBrowseObject>Arabirimi bir yapılandırma Gözat nesnesi diğerinden ayırt etmek için kullanılır.

## <a name="see-also"></a>Ayrıca bkz.

- <xref:Microsoft.VisualStudio.Shell.Interop.__VSFPROPID>