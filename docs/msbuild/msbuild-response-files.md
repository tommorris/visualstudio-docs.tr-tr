---
title: "MSBuild yanıt dosyaları | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
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
caps.latest.revision: "3"
author: kempb
ms.author: kempb
manager: ghogen
ms.openlocfilehash: a9ceab64ec0009dd143f42e1b94538690780f1bb
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="msbuild-response-files"></a>MSBuild Yanıt Dosyaları
Yanıt (.rsp) dosyaları MSBuild.exe komut satırı anahtarları içeren metin dosyalarıdır. Her anahtar ayrı bir satırda veya tüm anahtarları tek bir satırda olabilir. Yorum Satırları ile başlayan bir  **#**  simgesi. **@**  Anahtar MSBuild.exe için başka bir yanıt dosyası geçirmek için kullanılır.  
  
 Otomatik yanıt dosyası kullanan MSBuild.exe otomatik olarak bir proje oluşturulurken bir özel .rsp dosyasıdır. Bu dosya, MSBuild.rsp, MSBuild.exe ile aynı dizinde olmalıdır, aksi takdirde, bulunamayacaktır. MSBuild.exe için varsayılan komut satırı anahtarları belirtmek için bu dosyayı düzenleyebilirsiniz. Örneğin, bir projeyi derleme her zaman aynı Günlükçü kullanırsanız, ekleyebileceğiniz **/logger** geçiş için MSBuild.rsp ve bir proje yerleşik her zaman MSBuild.exe Günlükçü kullanır.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [MSBuild başvurusu](../msbuild/msbuild-reference.md)   
 [Komut satırı başvurusu](../msbuild/msbuild-command-line-reference.md)