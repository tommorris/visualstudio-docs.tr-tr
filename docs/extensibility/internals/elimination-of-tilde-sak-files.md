---
title: Ortadan kaldırılması ~ SAK dosyaları | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- temporary files
- ~sak files
- source control plug-ins, ~SAK files
ms.assetid: 5277b5fa-073b-4bd1-8ba1-9dc913aa3c50
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 61227652bf191280f69466f127c4a400ea43856e
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
ms.locfileid: "31129647"
---
# <a name="elimination-of-sak-files"></a>Ortadan kaldırılması ~ SAK dosyaları
Kaynak Denetim eklentisi API 1.2 içindeki ~ SAK dosyaları değiştirilir yetenek bayrakları ve kaynak denetim eklentisi MSSCCPRJ dosyasını ve paylaşılan kullanıma destekleyip desteklemediğini algılamak yeni işlevler tarafından.  
  
## <a name="sak-files"></a>~ SAK dosyaları  
 Visual Studio .NET 2003 oluşturulan geçici dosyalar önekine sahip ~ SAK. Bu dosyalar, kaynak denetim eklentisi destekleyip desteklemediğini belirlemek için kullanılır:  
  
-   MSSCCPRJ. SCC dosyası.  
  
-   Birden çok (paylaşılan) kullanıma alma.  
  
 Kaynak Denetim eklentisi API 1.2 ile sağlanan gelişmiş işlevleri desteklemek eklentiler için yeni özellikleri, bayrakları ve İşlevler, aşağıdaki bölümlerde ayrıntılı kullanımı ile geçici dosyalar oluşturmadan bu yetenekleri IDE algılayabilir.  
  
## <a name="new-capability-flags"></a>Yeni yetenek bayrakları  
 `SCC_CAP_SCCFILE`  
  
 `SCC_CAP_MULTICHECKOUT`  
  
## <a name="new-functions"></a>Yeni işlevleri  
 [SccWillCreateSccFile](../../extensibility/sccwillcreatesccfile-function.md)  
  
 [SccIsMultiCheckoutEnabled](../../extensibility/sccismulticheckoutenabled-function.md)  
  
 Kaynak Denetim eklentisi birden çok (paylaşılan) kullanıma destekleyen sonra onu tanımlandığı `SCC_CAP_MULTICHECKOUT` yeteneği ve uygulayan `SccIsMultiCheckOutEnabled` işlevi. Bu işlev, herhangi bir kaynak tarafından denetlenen projeleri üzerinde kullanıma alma işlemi oluştuğunda çağrılır.  
  
 Kaynak Denetim eklentisi oluşturma ve bir MSSCCPRJ kullanımını destekliyorsa. SCC dosya, ardından bildirir `SCC_CAP_SCCFILE` yeteneği ve uygulayan [SccWillCreateSccFile](../../extensibility/sccwillcreatesccfile-function.md). Bu işlev, dosyaların bir listesini çağrılır. İşlevi döndürür `TRUE/FALSE` Visual Studio bir MSSCCPRJ kullanması gerekip gerekmediğini belirtmek her bir dosya için. Bunun için SCC dosya. Kaynak Denetim eklentisi bu yeni özellikler ve İşlevler değil desteklemeyi seçerse, bu dosyaları oluşturulmasını devre dışı bırakmak için aşağıdaki kayıt defteri anahtarını kullanabilirsiniz:  
  
 [HKEY_CURRENT_USER\Software\Microsoft\VisualStudio\8.0\SourceControl] "DoNotCreateTemporaryFilesInSourceControl" = dword: 00000001  
  
> [!NOTE]
>  Bu kayıt defteri anahtarı DWORD: 00000000 için ayarlarsanız, varolmayan olan anahtarına eşdeğerdir ve Visual Studio hala geçici dosyalar oluşturma dener. Ancak, kayıt defteri anahtarı DWORD: 00000001 için ayarlarsanız, geçici dosyaları oluşturmak Visual Studio denemez. Bunun yerine eklenti kaynak denetimi MSSCCPRJ desteklemiyor varsayar. SCC dosya ve paylaşılan kullanıma desteklemez.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Kaynak Denetimi Eklentisi API Sürümü 1.2’deki Yenilikler](../../extensibility/internals/what-s-new-in-the-source-control-plug-in-api-version-1-2.md)