---
title: WinRTError nesnesi (JavaScript) | Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-javascript
ms.tgt_pltfrm: ''
ms.topic: language-reference
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- WinRTError object [JavaScript]
- JavaScript, WinRTError object
ms.assetid: d75ab8e5-e729-4d86-90fd-ea228c30dd66
caps.latest.revision: 9
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 11b339b4fc3c4bd4f34416ffd98b8f9c3f288f98
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
ms.locfileid: "24791780"
---
# <a name="winrterror-object-javascript"></a>WinRTError Nesnesi (JavaScript)
Windows çalışma zamanı çağrısı bir hata olduğunu gösteren bir HRESULT döndürüldüğünde, JavaScript için özel bir Windows çalışma zamanı hatası dönüştürür. Yalnızca kullanılabilir [!INCLUDE[win8_appname_long](../../javascript/includes/win8-appname-long-md.md)] Windows çalışma zamanı mevcut olduğunda uygulamaları genel JavaScript ad alanı bir parçası olarak.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
errorObj = new WinRTError();  
  
```  
  
## <a name="remarks"></a>Açıklamalar  
 WinRTError hata türü Windows çalışma zamanı API'leri kaynaklanan hatalar için kullanılır.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek, bir WinRTError nasıl oluşturulur ve yakalanan gösterir.  
  
```JavaScript  
try {  
            Windows.Storage.ApplicationData.localFolder.createFileAsync("sample.txt");  
        } catch (err) {  
            var n = err;  
        }  
  
```  
  
## <a name="methods"></a>Yöntemler  
 WinRTError nesnesi hiçbir yöntemlerine sahiptir.  
  
## <a name="properties"></a>Özellikler  
 WinRTError nesnesi olarak aynı özelliklere sahip [hata nesnesi](../../javascript/reference/error-object-javascript.md) nesnesi.  
  
## <a name="requirements"></a>Gereksinimler  
 WinRTError nesnesi yalnızca desteklenen [!INCLUDE[win8_appname_long](../../javascript/includes/win8-appname-long-md.md)] Internet Explorer'da uygulamalar.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Hata nesnesi](../../javascript/reference/error-object-javascript.md)