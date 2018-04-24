---
title: 'Güvenlik Uyarısı: Hata ayıklayıcı güvenilmeyen komut yürütmeli | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
f1_keywords:
- vs.debug.sourceserver.securityalert
dev_langs:
- CSharp
- VB
- FSharp
- C++
ms.assetid: e5c004b3-b364-4098-ac98-770076ca9981
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 77554795772a5a9e2ce5d9bbe9f620923bc20184
ms.sourcegitcommit: 3d10b93eb5b326639f3e5c19b9e6a8d1ba078de1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/18/2018
---
# <a name="security-warning-debugger-must-execute-untrusted-command"></a>Güvenlik Uyarısı: Hata Ayıklayıcı Güvenilmeyen Komut Yürütmeli
Kaynak sunucu kullanırken bu uyarı iletişim kutusu görüntülenir. Hata ayıklayıcı kaynak kodu almak için gereken komut srcsvr.ini dosyasında yer alan kaynak sunucu için güvenilen komutları listesinde olduğunu belirtir. Bu geçerli bir komut ise, srcsvr.ini dosyasına ekleyebilirsiniz. Aksi takdirde, bu çalışmamalıdır. Daha fazla bilgi için bkz: [belirtin simge (.pdb) ve kaynak dosyaları](../debugger/specify-symbol-dot-pdb-and-source-files-in-the-visual-studio-debugger.md).  
  
## <a name="message-text"></a>İleti metni  
 **Hata ayıklayıcı kaynak kodu kaynak sunucudan elde etmek için aşağıdaki güvenilmeyen komutu yürütmeniz gerekir.**  
  
 **Hata ayıklama simgesi dosyası ise (\*.pdb) olan olmayan bir bilinen ve güvenilen kaynaktan, bu komut geçersiz ya da çalıştırmak tehlikeli olabilir.**  
  
 **Bu komutu çalıştırmak istiyor musunuz?**  
  
## <a name="uielement-list"></a>UIElement Listesi  
 Metin kutusu  
 .Pdb dosyasından çalıştırmak için komutu.  
  
 Çalıştır  
 Çalıştırılacak komut izin verir.  
  
 Çalıştırma  
 Komutu yürütme ve kaynak sunucudan dosya indirme durdurun.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Simge (.pdb) belirtin ve kaynak dosyaları](../debugger/specify-symbol-dot-pdb-and-source-files-in-the-visual-studio-debugger.md)   
 [Hata ayıklama güvenliği](../debugger/debugger-security.md)   
 [Kaynak sunucusu](http://msdn.microsoft.com/library/windows/desktop/ms680641\(v=vs.85\).aspx)