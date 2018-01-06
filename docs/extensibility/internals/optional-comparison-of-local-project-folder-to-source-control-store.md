---
title: "Kaynak Denetim deposunu proje klasörüne karşılaştırma | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- source control plug-ins, comparing versions
- source control plug-ins, local project folders
ms.assetid: 65217e8b-15a6-4446-92b0-4cff1c6220f5
caps.latest.revision: "14"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: cbf4e9f2ccbe895db79115949818345c62245f71
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="optional-comparison-of-local-project-folder-to-source-control-store"></a>Kaynak Denetim deposunu yerel proje klasörüne isteğe bağlı karşılaştırması
Eklenti API yerel proje klasörünü ve kaynak denetimi karşılaştırması işlevlerini kullanarak gerçekleştirilir 1.2 kaynağında kontrol [SccDirQueryInfo](../../extensibility/sccdirqueryinfo-function.md) ve [SccDirDiff](../../extensibility/sccdirdiff-function.md).  
  
 İçinde **Çözüm Gezgini**, tek bir dosyayı yerine bir klasör seçilirse, **karşılaştırmak sürümleri** kısayol menüsünü çağırır yeni [SccDirQueryInfo](../../extensibility/sccdirqueryinfo-function.md) ve [ SccDirDiff](../../extensibility/sccdirdiff-function.md) eklenti kaynak denetiminde.  
  
## <a name="new-capability-flags"></a>Yeni yetenek bayrakları  
 `SCC_CAP_DIRECTORYDIFF`  
  
 `SCC_CAP_DIRECTORYCHECKOUT`  
  
## <a name="new-functions"></a>Yeni işlevleri  
 [SccDirDiff](../../extensibility/sccdirdiff-function.md)  
  
 [SccDirQueryInfo](../../extensibility/sccdirqueryinfo-function.md)  
  
 `SccDirQueryInfo` İşlevi çağrılmadan önce `SccDirDiff` çalışma dizini kaynak denetimli olup olmadığını belirlemek için. `SccDirDiff` İşlevi geçerli yerel dizin ve karşılık gelen kaynak denetimi klasör arasındaki farkları görüntüler. Bu komut eklentisinin dizine değişikliklerin listesini görüntülemek için kaynak denetimi sorar. Kaynak Denetim eklentisi farkları görüntülemek için kendi kullanıcı Arabirimi sağlar.  
  
> [!NOTE]
>  Bu işlev olarak aynı komutu bayrakları kullanır [SccDiff](../../extensibility/sccdiff-function.md). Kaynak denetimi eklenti sağlayıcısı, dizinler için "hızlı fark" işlemi desteklemeyen tercih edebilirsiniz.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Kaynak Denetimi Eklentisi API Sürümü 1.2’deki Yenilikler](../../extensibility/internals/what-s-new-in-the-source-control-plug-in-api-version-1-2.md)