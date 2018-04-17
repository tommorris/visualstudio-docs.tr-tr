---
title: SetEnv görevi | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: msbuild
ms.topic: conceptual
f1_keywords:
- vc.task.setenv
dev_langs:
- VB
- CSharp
- C++
- jsharp
- C++
helpviewer_keywords:
- MSBuild (Visual C++), tasks
- SetEnv task (MSBuild (Visual C++))
ms.assetid: fd9e4225-68cb-4608-8b27-468b0218c936
author: Mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 01c939d3d7a7f503e3f43d1b11047f0105a3ffa3
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="setenv-task"></a>SetEnv Görevi
Ayarlar veya belirtilen ortam değişkeninin değeri siler.  
  
## <a name="parameters"></a>Parametreler  
 Aşağıdaki tabloda parametrelerinin açıklanmaktadır **SetEnv** görev.  
  
|Parametre|Açıklama|  
|---------------|-----------------|  
|**Ad**|Gerekli **dize** parametresi.<br /><br /> Bir ortam değişkeni adı.|  
|**OutputEnvironmentVariable**|İsteğe bağlı **dize** çıkış parametresi.<br /><br /> Tarafından belirtilen ortam değişkenine atanan değeri içeren **adı** parametresi.|  
|**önek**|Zorunlu `Boolean` parametresi.<br /><br /> Varsa `true`, değerini art arda ekler **değeri** parametresi tarafından belirtilen ortam değişkeninin değerini önce **adı** parametresi ve ardından sonucu ortama atar değişkeni. Varsa `false`, yalnızca değeri atar **değeri** ortam değişkeni parametresi.|  
|**Hedef**|İsteğe bağlı **dize** parametresi.<br /><br /> Bir ortam değişkeni depolanacağı konumu belirtir. Belirtin "`User`"veya"`Machine`".<br /><br /> Daha fazla bilgi için "EnvironmentVariableTarget numaralandırma" bakın [MSDN](http://go.microsoft.com/fwlink/?LinkId=737) Web sitesi.|  
|**Değer**|İsteğe bağlı **dize** parametresi.<br /><br /> Tarafından belirtilen ortam değişkenine atanan değeri **adı** parametresi. Varsa **değeri** boş ve değişken var, değişkeni silinir. Değişkeni yoksa, işlem gerçekleştirilemiyor olsa bile hata oluşmaz.<br /><br /> Daha fazla bilgi için "Environment::SetEnvironmentVariable yöntemi" bakın [MSDN](http://go.microsoft.com/fwlink/?LinkId=737) Web sitesi.|  
  
## <a name="remarks"></a>Açıklamalar  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Görev başvurusu](../msbuild/msbuild-task-reference.md)