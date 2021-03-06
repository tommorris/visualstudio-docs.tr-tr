---
title: MSBuild yanıt dosyaları | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: msbuild
ms.topic: reference
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
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 83f8e5ad4522a47eaea978b14678fe134b4faa8e
ms.sourcegitcommit: 8ee7efb70a1bfebcb6dd9855b926a4ff043ecf35
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/17/2018
ms.locfileid: "39081598"
---
# <a name="msbuild-response-files"></a>MSBuild yanıt dosyaları
Yanıt (*.rsp*) dosyalar içeren metin dosyalarını *MSBuild.exe* komut satırı anahtarları. Her anahtar ayrı bir satıra olabilir veya tek bir satırda tüm anahtarlar olabilir. Yorum Satırları ile giriş yapılmış bir **#** simgesi. **@** Başka bir yanıt dosyasına aktarmak için kullanılan anahtar *MSBuild.exe*.  
  
## <a name="msbuildrsp"></a>MSBuild.rsp
Özel bir otomatik yanıt dosyasıdır *.rsp* dosya *MSBuild.exe* otomatik olarak bir proje derlenirken kullanır. Bu dosya *MSBuild.rsp*, aynı dizinde olmalıdır *MSBuild.exe*, aksi takdirde, bulunamayacaktır. Varsayılan komut satırı anahtarları için belirtmek için bu dosyayı düzenleyebilirsiniz *MSBuild.exe*. Örneğin, aynı Günlükçü kullanıyorsanız, bir projeyi her derlediğinizde, ekleyebileceğiniz **/logger** geçin *MSBuild.rsp*, ve *MSBuild.exe* Günlükçü her zaman kullanacağı bir Proje oluşturulur.  

## <a name="directorybuildrsp"></a>Directory.Build.rsp
Sürüm 15.6 ve üzeri MSBuild adlı bir dosya için projenin üst dizininde arar *Directory.Build.rsp*.  Bu, varsayılan bağımsız değişkenleri komut satırı derlemeleri sırasında sağlamak için kaynak kodu deposu yardımcı olabilir.  Ayrıca, barındırılan derlemeler komut satırı bağımsız değişkenlerini belirtmek için de kullanılabilir.

## <a name="see-also"></a>Ayrıca bkz.  
 [MSBuild başvurusu](../msbuild/msbuild-reference.md)   
 [Komut satırı başvurusu](../msbuild/msbuild-command-line-reference.md)