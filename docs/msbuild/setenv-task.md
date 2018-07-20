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
ms.openlocfilehash: e2d9cec2c76b2159e14b1e7abe19b93ab91f6688
ms.sourcegitcommit: 0e5289414d90a314ca0d560c0c3fe9c88cb2217c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/19/2018
ms.locfileid: "39153780"
---
# <a name="setenv-task"></a>SetEnv görevi
Belirtilen ortam değişkeninin değerini siler veya ayarlar.  
  
## <a name="parameters"></a>Parametreler  
 Parametreleri aşağıdaki tabloda açıklanmıştır **SetEnv** görev.  
  
|Parametre|Açıklama|  
|---------------|-----------------|  
|**Ad**|Gerekli **dize** parametresi.<br /><br /> Bir ortam değişkeninin adı.|  
|**OutputEnvironmentVariable**|İsteğe bağlı **dize** çıkış parametresi.<br /><br /> Tarafından belirtilen ortam değişkenine atanan değeri içeren **adı** parametresi.|  
|**Ön eki**|Zorunlu `Boolean` parametresi.<br /><br /> Varsa `true`, değerini art arda ekler **değer** parametresi tarafından belirtilen ortam değişkeninin değerini önce **adı** parametresi ve ardından sonucu ortama atar değişken. Varsa `false`, yalnızca değerini atar **değer** ortam değişkenine parametresi.|  
|**Hedef**|İsteğe bağlı **dize** parametresi.<br /><br /> Bir ortam değişkeni depolandığı konumu belirtir. "Kullanıcı" veya "Machine" belirtin.<br /><br /> Daha fazla bilgi için [EnvironmentVariableTarget numaralandırma](https://msdn.microsoft.com/library/system.environmentvariabletarget(v=vs.110).aspx) MSDN Web sitesinde.|  
|**Değer**|İsteğe bağlı **dize** parametresi.<br /><br /> Tarafından belirtilen ortam değişkenine atanan değeri **adı** parametresi. Varsa **değer** boştur ve değişken var, değişken silindi. Değişkeni mevcut değilse işlemin gerçekleştirilmesinden olsa bile hata oluşmaz.<br /><br /> Daha fazla bilgi için [Environment::SetEnvironmentVariable yöntemi](https://msdn.microsoft.com/library/96xafkes(v=vs.110).aspx) MSDN Web sitesinde.|  
  
## <a name="see-also"></a>Ayrıca bkz.  
 [Görev başvurusu](../msbuild/msbuild-task-reference.md)