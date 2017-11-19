---
title: "VCMessage görevi | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vc.task.vcmessage
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
caps.latest.revision: "7"
author: kempb
ms.author: kempb
manager: ghogen
ms.openlocfilehash: 16ed7f4207a65915afbf18a496a0152e04e9a8d0
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="vcmessage-task"></a>VCMessage Görevi
Uyarı günlükleri ve derleme sırasında hata iletileri.  
  
## <a name="remarks"></a>Açıklamalar  
 Bu görev için Visual C++ MSBuild uygulamak yardımcı olur ve kullanıcı tarafından çağrılması amaçlanmamıştır. Daha fazla bilgi için bkz. <xref:Microsoft.Build.Utilities.TaskLoggingHelper>.  
  
## <a name="parameters"></a>Parametreler  
 Aşağıdaki tabloda parametrelerinin açıklanmaktadır **VCMessage** görev.  
  
|Parametre|Açıklama|  
|---------------|-----------------|  
|**Bağımsız değişkenler**|İsteğe bağlı **dize** parametresi.<br /><br /> Görüntülenecek iletileri noktalı virgülle ayrılmış listesi.|  
|**Kod**|Gerekli **dize** parametresi.<br /><br /> İleti niteleyen bir hata numarası.|  
|**Türü**|İsteğe bağlı **dize** parametresi.<br /><br /> İleti yayma türünü belirtir. Belirtin `"Warning"` bir uyarı iletisi yaymak üzere veya `"Error"` bir hata iletisi yaymak üzere.|  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Görev başvurusu](../msbuild/msbuild-task-reference.md)