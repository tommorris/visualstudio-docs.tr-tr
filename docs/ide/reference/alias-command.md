---
title: "Diğer ad komutu | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: tools.alias
helpviewer_keywords:
- aliases, Visual Studio commands
- commands, aliases
- Tools.Alias command
- command aliases
- alias command
ms.assetid: bdf857df-b5d5-450f-8c10-a6fd4dccc130
caps.latest.revision: "12"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: cac24838cd848770c45794637620b70cea3e1bd6
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="alias-command"></a>Diğer Ad Komutu
Tam komut, tam komut ve bağımsız değişkenler için yeni bir diğer ad veya başka bir diğer ad oluşturur.  
  
> [!TIP]
>  Yazmaya `>alias` herhangi bir bağımsız değişken görüntüler olmadan diğer adlar ve tanımlarını geçerli listesi.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
Tools.Alias [/delete] [/reset] [aliasname] [aliasstring]  
```  
  
## <a name="arguments"></a>Arguments  
 `aliasname`  
 İsteğe bağlı. Yeni diğer ad. İçin hiçbir değer sağlanmazsa `aliasname`, geçerli diğer adlar ve tanımları listesi görüntülenir.  
  
 `aliasstring`  
 İsteğe bağlı. Tam komut adı veya var olan diğer ad ve bir diğer ad olarak oluşturmak istediğiniz herhangi bir parametre. İçin hiçbir değer sağlanmazsa `aliasstring`, belirtilen diğer ad görüntüler için diğer ad ve diğer ad dizesi.  
  
## <a name="switches"></a>Anahtarlar  
 / DELETE veya/DEL ya da /d  
 İsteğe bağlı. Otomatik Tamamlama kaldırma belirtilen diğer ad siler.  
  
 / Reset  
 İsteğe bağlı. Önceden tanımlanmış diğer adların listesi özgün ayarlarına sıfırlar. Diğer bir deyişle, tüm ön tanımlı diğer adlar geri yükler ve tüm kullanıcı tanımlı diğer adlar kaldırır.  
  
## <a name="remarks"></a>Açıklamalar  
 Diğer adlar komutları temsil ettiği bunlar komut satırı başında yer alması gerekir.  
  
 Bu komut verilirken komutu hemen sonra anahtarları değil sonra diğer adlar içermelidir, aksi takdirde anahtar diğer ad dizesi bir parçası olarak dahil olacaktır.  
  
 `/reset` Anahtar diğer adları geri önce bir onay ister. Kısa form, yoktur `/reset`.  
  
## <a name="examples"></a>Örnekler  
 Bu örnek, yeni bir ad oluşturur `upper`, tam komut Edit.MakeUpperCase.  
  
```  
>Tools.Alias upper Edit.MakeUpperCase  
```  
  
 Bu örnek, diğer siler `upper`.  
  
```  
>Tools.alias /delete upper  
```  
  
 Bu örnekte, tüm geçerli diğer adlar ve tanımları listesini görüntüler.  
  
```  
>Tools.Alias  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Visual Studio komutları](../../ide/reference/visual-studio-commands.md)   
 [Komut penceresi](../../ide/reference/command-window.md)   
 [Bul/komut kutusu](../../ide/find-command-box.md)   
 [Visual Studio komut diğer adları](../../ide/reference/visual-studio-command-aliases.md)