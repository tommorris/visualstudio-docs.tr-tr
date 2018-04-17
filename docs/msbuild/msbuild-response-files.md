---
title: MSBuild yanıt dosyaları | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: msbuild
ms.topic: conceptual
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
author: Mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: c619a21588ed2026e360e01be05af7012cf1304b
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="msbuild-response-files"></a>MSBuild Yanıt Dosyaları
Yanıt (.rsp) dosyaları MSBuild.exe komut satırı anahtarları içeren metin dosyalarıdır. Her anahtar ayrı bir satırda veya tüm anahtarları tek bir satırda olabilir. Yorum Satırları ile başlayan bir **#** simgesi. **@** Anahtar MSBuild.exe için başka bir yanıt dosyası geçirmek için kullanılır.  
  
## <a name="msbuildrsp"></a>MSBuild.rsp
Otomatik yanıt dosyası kullanan MSBuild.exe otomatik olarak bir proje oluşturulurken bir özel .rsp dosyasıdır. Bu dosya, MSBuild.rsp, MSBuild.exe ile aynı dizinde olmalıdır, aksi takdirde, bulunamayacaktır. MSBuild.exe için varsayılan komut satırı anahtarları belirtmek için bu dosyayı düzenleyebilirsiniz. Örneğin, bir projeyi derleme her zaman aynı Günlükçü kullanırsanız, ekleyebileceğiniz **/logger** geçiş için MSBuild.rsp ve bir proje yerleşik her zaman MSBuild.exe Günlükçü kullanır.  

## <a name="directorybuildrsp"></a>Directory.Build.rsp
Sürüm 15,6 ve üzeri, MSBuild proje adlı bir dosya için üst dizinleri arayacaktır `Directory.Build.rsp`.  Varsayılan bağımsız değişkenler sırasında komut satırı derlemeleri sağlamak için bir kaynak kod deposu yararlı olabilir.  Ayrıca, barındırılan derlemelerin komut satırı bağımsız değişkenlerini belirtmek için de kullanılabilir.

## <a name="see-also"></a>Ayrıca Bkz.  
 [MSBuild başvurusu](../msbuild/msbuild-reference.md)   
 [Komut Satırı Başvurusu](../msbuild/msbuild-command-line-reference.md)