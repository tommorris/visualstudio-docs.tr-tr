---
title: MSBuild yanıt dosyaları | Microsoft Docs
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
- response files, MSBuild
- MSBuild, response files
- MSBuild, .rsp files
- .rsp files
ms.assetid: 9f53987b-20ee-470a-ab62-fce997bb5e15
caps.latest.revision: 6
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 71fdc29db3e2af66c85637648bb0703e7f7d80c1
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42630945"
---
# <a name="msbuild-response-files"></a>MSBuild Yanıt Dosyaları
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [MSBuild yanıt dosyaları](https://docs.microsoft.com/visualstudio/msbuild/msbuild-response-files).  
  
  
Yanıt (.rsp), MSBuild.exe komut satırı anahtarları içeren metin dosyalarını dosyalarıdır. Her anahtar ayrı bir satıra olabilir veya tek bir satırda tüm anahtarlar olabilir. Yorum Satırları ile giriş yapılmış bir **#** simgesi. **@** Başka bir yanıt dosyası MSBuild.exe'ye geçirilecek anahtar kullanılır.  
  
 Otomatik yanıt dosyası bir proje derlenirken MSBuild.exe kullanan bir özel .rsp dosyasıdır. Bu dosya, MSBuild.rsp, MSBuild.exe ile aynı dizinde olmalıdır, aksi takdirde, bulunmaz. Varsayılan komut satırında MSBuild.exe geçer belirtmek için bu dosyayı düzenleyebilirsiniz. Örneğin, aynı Günlükçü kullanıyorsanız, bir projeyi her derlediğinizde, ekleyebileceğiniz **/logger** geçiş için MSBuild.rsp ve bir proje her zaman MSBuild.exe Günlükçü kullanır.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [MSBuild başvurusu](../msbuild/msbuild-reference.md)   
 [Komut Satırı Başvurusu](../msbuild/msbuild-command-line-reference.md)



