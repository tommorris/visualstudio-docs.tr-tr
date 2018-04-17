---
title: VCMessage görevi | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: msbuild
ms.topic: conceptual
f1_keywords:
- vc.task.vcmessage
dev_langs:
- VB
- CSharp
- C++
- jsharp
- C++
helpviewer_keywords:
- VCMessage task (MSBuild (Visual C++))
- MSBuild (Visual C++), VCMessage task
ms.assetid: 956675fd-05dc-40b4-856f-616145103498
author: Mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 668379b5c22dfe95d4b7465d348874020bfc3b3c
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="vcmessage-task"></a>VCMessage Görevi
Uyarı günlükleri ve derleme sırasında hata iletileri.  
  
## <a name="remarks"></a>Açıklamalar  
 Bu görev için Visual C++ MSBuild uygulamak yardımcı olur ve kullanıcı tarafından çağrılması amaçlanmamıştır. Daha fazla bilgi için bkz. <xref:Microsoft.Build.Utilities.TaskLoggingHelper>.  
  
## <a name="parameters"></a>Parametreler  
 Aşağıdaki tabloda parametrelerinin açıklanmaktadır **VCMessage** görev.  
  
|Parametre|Açıklama|  
|---------------|-----------------|  
|**Bağımsız Değişkenler**|İsteğe bağlı **dize** parametresi.<br /><br /> Görüntülenecek iletileri noktalı virgülle ayrılmış listesi.|  
|**Kod**|Gerekli **dize** parametresi.<br /><br /> İleti niteleyen bir hata numarası.|  
|**Türü**|İsteğe bağlı **dize** parametresi.<br /><br /> İleti yayma türünü belirtir. Belirtin `"Warning"` bir uyarı iletisi yaymak üzere veya `"Error"` bir hata iletisi yaymak üzere.|  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Görev başvurusu](../msbuild/msbuild-task-reference.md)