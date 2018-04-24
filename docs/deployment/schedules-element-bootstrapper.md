---
title: '&lt;Zamanlamalar&gt; öğe (Önyükleyici) | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-deployment
ms.topic: conceptual
dev_langs:
- FSharp
- VB
- CSharp
- C++
helpviewer_keywords:
- <Schedules> element [bootstrapper]
ms.assetid: 28d094cf-64f5-42b1-bd8a-3697082aab4f
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: a4cbc6b4f5ebd400d90466ccfa353d679a766580
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/19/2018
---
# <a name="ltschedulesgt-element-bootstrapper"></a>&lt;Zamanlamalar&gt; öğe (Önyükleyici)
`Schedules` Ögesinin `Schedule` tarafından tanımlanan hangi komutların belirli zamanlarda tanımlamak öğeleri `Command` öğesi çalıştırılmalıdır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
<Schedules>  
    <Schedule  
        Name  
    >  
        <BuildList />  
        <BeforePackage />  
        <AfterPackage />  
    </Schedule>  
</Schedules>  
```  
  
## <a name="elements-and-attributes"></a>Öğeleri ve öznitelikleri  
 `Schedules` Bir alt öğedir `Product` öğesi. Her `Product` öğesi en fazla bir olabilir `Schedules` öğesi. `Schedules` Öğesi özniteliklere sahip değildir.  
  
## <a name="schedule"></a>Zamanlama  
 `Schedule` Bir alt öğedir `Schedules` öğesi. A `Schedules` öğesinin en az bir olmalı `Schedule` öğesi.  
  
 `Schedule` Aşağıdaki özniteliklere sahiptir.  
  
|Öznitelik|Açıklama|  
|---------------|-----------------|  
|`Name`|Gerekli. Zamanlama öğesinin adı. Bu karşılık `ScheduleName` özelliği `Command` öğesi. Zaman bir `Command` adlandırılmış zamanlama başvuran tarafından belirtilen saatte yalnızca yürütülecek `Schedule` öğesi. Zamanlamalar de ilişkilendirilebilir `FailIf` ve `BypassIf` belirtilen bir zamanlamayla yürütme için bu koşul testlerini kısıtlamak öğeleri. Daha fazla bilgi için bkz: [ \<komutları > öğesi](../deployment/commands-element-bootstrapper.md).|  
  
 Belirli bir `Schedule` öğe aşağıdaki alt tam olarak birine sahip.  
  
## <a name="buildlist"></a>BuildList  
 `BuildList` Öğesi hemen önyükleme uygulaması başladıktan sonra komut yürütme yükleyici bildirir.  
  
## <a name="beforepackage"></a>BeforePackage  
 `BeforePackage` Öğesi belirtilen paket yüklenmeden önce komut yürütme yükleyici bildirir.  
  
## <a name="afterpackage"></a>AfterPackage  
 `AfterPackage` Öğesi belirtilen paket yüklendikten sonra komut yürütme yükleyici bildirir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [\<Ürün > öğesi](../deployment/product-element-bootstrapper.md)   
 [Ürün ve Paket Şema Başvurusu](../deployment/product-and-package-schema-reference.md)