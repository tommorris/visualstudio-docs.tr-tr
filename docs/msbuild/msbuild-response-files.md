---
title: "MSBuild yanıt dosyaları | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: msbuild
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
caps.latest.revision: 
author: Mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: 40a9f7b6e1456c511e70937ac6a1cff23dad30d0
ms.sourcegitcommit: a80e7ef2f0a0f6d906a44f4d696aeb208bc1ad70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/21/2018
---
# <a name="msbuild-response-files"></a>MSBuild Yanıt Dosyaları
Yanıt (.rsp) dosyaları MSBuild.exe komut satırı anahtarları içeren metin dosyalarıdır. Her anahtar ayrı bir satırda veya tüm anahtarları tek bir satırda olabilir. Yorum Satırları ile başlayan bir  **#**  simgesi.  **@**  Anahtar MSBuild.exe için başka bir yanıt dosyası geçirmek için kullanılır.  
  
## <a name="msbuildrsp"></a>MSBuild.rsp
Otomatik yanıt dosyası kullanan MSBuild.exe otomatik olarak bir proje oluşturulurken bir özel .rsp dosyasıdır. Bu dosya, MSBuild.rsp, MSBuild.exe ile aynı dizinde olmalıdır, aksi takdirde, bulunamayacaktır. MSBuild.exe için varsayılan komut satırı anahtarları belirtmek için bu dosyayı düzenleyebilirsiniz. Örneğin, bir projeyi derleme her zaman aynı Günlükçü kullanırsanız, ekleyebileceğiniz **/logger** geçiş için MSBuild.rsp ve bir proje yerleşik her zaman MSBuild.exe Günlükçü kullanır.  

## <a name="directorybuildrsp"></a>Directory.Build.rsp
Sürüm 15,6 ve üzeri, MSBuild proje adlı bir dosya için üst dizinleri arayacaktır `Directory.Build.rsp`.  Varsayılan bağımsız değişkenler sırasında komut satırı derlemeleri sağlamak için bir kaynak kod deposu yararlı olabilir.  Ayrıca, barındırılan derlemelerin komut satırı bağımsız değişkenlerini belirtmek için de kullanılabilir.

## <a name="see-also"></a>Ayrıca Bkz.  
 [MSBuild başvurusu](../msbuild/msbuild-reference.md)   
 [Komut Satırı Başvurusu](../msbuild/msbuild-command-line-reference.md)