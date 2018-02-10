---
title: "SetEnv görevi | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: msbuild
ms.tgt_pltfrm: 
ms.topic: article
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
caps.latest.revision: 
author: Mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: ffcbbff4b04bcfa48fdf4d4812be033c659322af
ms.sourcegitcommit: 205d15f4558315e585c67f33d5335d5b41d0fcea
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/09/2018
---
# <a name="setenv-task"></a>SetEnv Görevi
Ayarlar veya belirtilen ortam değişkeninin değeri siler.  
  
## <a name="parameters"></a>Parametreler  
 Aşağıdaki tabloda parametrelerinin açıklanmaktadır **SetEnv** görev.  
  
|Parametre|Açıklama|  
|---------------|-----------------|  
|**Ad**|Gerekli **dize** parametresi.<br /><br /> Bir ortam değişkeni adı.|  
|**OutputEnvironmentVariable**|İsteğe bağlı **dize** çıkış parametresi.<br /><br /> Tarafından belirtilen ortam değişkenine atanan değeri içeren **adı** parametresi.|  
|**Prefix**|Zorunlu `Boolean` parametresi.<br /><br /> Varsa `true`, değerini art arda ekler **değeri** parametresi tarafından belirtilen ortam değişkeninin değerini önce **adı** parametresi ve ardından sonucu ortama atar değişkeni. Varsa `false`, yalnızca değeri atar **değeri** ortam değişkeni parametresi.|  
|**Hedef**|İsteğe bağlı **dize** parametresi.<br /><br /> Bir ortam değişkeni depolanacağı konumu belirtir. Belirtin "`User`"veya"`Machine`".<br /><br /> Daha fazla bilgi için "EnvironmentVariableTarget numaralandırma" bakın [MSDN](http://go.microsoft.com/fwlink/?LinkId=737) Web sitesi.|  
|**Değer**|İsteğe bağlı **dize** parametresi.<br /><br /> Tarafından belirtilen ortam değişkenine atanan değeri **adı** parametresi. Varsa **değeri** boş ve değişken var, değişkeni silinir. Değişkeni yoksa, işlem gerçekleştirilemiyor olsa bile hata oluşmaz.<br /><br /> Daha fazla bilgi için "Environment::SetEnvironmentVariable yöntemi" bakın [MSDN](http://go.microsoft.com/fwlink/?LinkId=737) Web sitesi.|  
  
## <a name="remarks"></a>Açıklamalar  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Görev başvurusu](../msbuild/msbuild-task-reference.md)