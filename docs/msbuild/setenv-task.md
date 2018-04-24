---
title: SetEnv görevi | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: msbuild
ms.topic: reference
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
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: ec47adec3a9c979a21a543f2c073c440384b26d1
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/19/2018
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