---
title: Kaynak Denetimi Eklentisi oluşturma | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- plug-ins, source control
- source control plug-ins
- source control [Visual Studio SDK], plug-ins
ms.assetid: c7e69fa4-150e-469a-a6fc-fa1260bdbb07
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 04c6125004aaf2740b54acdce91bef032647c6e5
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="creating-a-source-control-plug-in"></a>Kaynak Denetimi Eklentisi oluşturma
Visual Studio SDK'sı için kaynak denetimi özelliği eklemenize olanak tanıyan kaynakları sağlar [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] tümleşik geliştirme ortamı (IDE). Kaynak Denetim eklentisi bu belgede özetlenen API ile uyumlu herhangi bir eklenti DLL kullanmanıza olanak sağlar.  
  
## <a name="in-this-section"></a>Bu Bölümde  
 [Başlarken](../../extensibility/internals/getting-started-with-source-control-plug-ins.md)  
 Kaynak Denetim Eklentisi yüklemeyi açıklar ve şu anda kullanılabilir kaynak denetim eklentisi API sürümleri vurgular.  
  
 [Mimari](../../extensibility/internals/source-control-plug-in-architecture.md)  
 Kaynak Denetim eklentisi ile tümleştirilmesi açıklamak için bir mimari diyagramı kullanan [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] IDE.  
  
 [Kaynak Denetimi Eklentileri için Test Kılavuzu](../../extensibility/internals/test-guide-for-source-control-plug-ins.md)  
 Test işlemi eklenti kaynak denetimi ve yükleme konusunda rehberlik sağlar.  
  
## <a name="related-sections"></a>İlgili Bölümler  
 [Kaynak Denetimi VSPackage’ı Oluşturma](../../extensibility/internals/creating-a-source-control-vspackage.md)  
 Kaynak denetiminin yalnızca kaynak denetim işlevselliği sağlar ancak değiştirir VSPackage nasıl oluşturulacağını anlatır [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] kaynak denetim UI.  
  
 [Kaynak Denetimi Eklentileri](../../extensibility/source-control-plug-ins.md)  
 Kaynak Denetim eklentisi API'ndaki tüm öğelerin listesi sağlar.  
  
 [Kaynak Denetimi](../../extensibility/internals/source-control.md)  
 Kaynak denetimi tümleşik bir özellik olarak uygulamak için seçenekleri açıklar [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)].