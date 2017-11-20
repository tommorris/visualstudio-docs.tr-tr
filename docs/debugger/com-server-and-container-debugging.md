---
title: "COM sunucusunda ve kapsayıcısında hata ayıklama | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vs.debug.com
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords:
- ActiveX control container debugging [Visual Studio]
- debugging ActiveX controls
- COM servers, debugging
- ActiveX controls, debugging
- COM [Visual Studio], debugging
ms.assetid: b7ce8696-ebb8-4354-a767-f76b8ada4ac1
caps.latest.revision: "20"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 558640368021f3556db479fc431c66dae266c9a1
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="com-server-and-container-debugging"></a>COM Sunucusunda ve Kapsayıcısında Hata Ayıklama
COM uygulamaları birkaç görev Programcı doğrudan denetim dışında gerçekleştirin. DLL'ler arasındaki iletişim, kullanım nesnelerde sayar ve Pano işlemleri birkaçı burada beklenmeyen davranışlarla karşılaşabilirsiniz alanları verilmiştir. Bu durumda, ilk adımınız sorunun kaynağı izlemektir.  
  
 Visual Studio hata ayıklayıcısı üzerinden ve kapsayıcılar ve sunucular içine Adımlama destekler. Bu uzaktan yordam çağrısı (RPC) adım yeteneğini içerir.  
  
##  <a name="BKMK_COMServerandContainerintheSameSolution"></a>Bir COM sunucusu ve aynı çözüm kapsayıcısında hata ayıklama  
 Bir COM sunucusu ve aynı çözüm içinde iki proje kullanarak kapsayıcı ayıklayabilirsiniz. Her proje ve hata ayıklama uygun kesme noktalarını ayarlayın. Kapsayıcı bir kesme noktası isabet Sunucusu'na bir çağrı yaptığında, kapsayıcı (diğer bir deyişle, bu hata ayıklama tamamlanana kadar) sunucu kodu döndürür kadar bekler.  
  
 Bir COM kapsayıcı hata ayıklama, standart bir program hata ayıklama için benzer. Bir geri çağırma (örneğin, veri kapsayıcısı uygulama sürükleyerek) oluşturan bir olay ayıklarken bir farktır. Bu durumda, geri çağırma işlevinin içinde kesme noktası ayarlamanız gerekir.  
  
##  <a name="BKMK_ServerApplicationWithoutContainerInformation"></a>Kapsayıcı bilgileri olmadan bir sunucu uygulaması hata ayıklama  
 Sunucu uygulaması hata ayıklamak başlangıç sahip değil veya kapsayıcı uygulamanız için hata ayıklama bilgilerini kullanmak istiyor musunuz, üç adımlık bir işlemdir şöyledir:  
  
1.  Sunucunun normal bir uygulama olarak hata ayıklama başlatılamıyor.  
  
2.  Kesme noktaları istediğiniz şekilde ayarlayın.  
  
3.  Kapsayıcı uygulamayı başlatın.  
  
##  <a name="BKMK_DebuggingaServerandDomainIsolationSDIApplication"></a>Bir sunucu ve etki alanı yalıtımı (SDI) uygulama hata ayıklama  
 SDI sunucu uygulaması ayıkladığınız varsa, belirtmeniz gerekir `/Embedding` veya `/Automation` içinde **komut satırı bağımsız değişkenleri** özelliğinde *proje* özellik sayfaları iletişim kutusu için C/C++, C# veya Visual Basic projeleri.  
  
 Bu komut satırı bağımsız değişkenleri ile başlatılan gibi sorgulamanıza kapsayıcıdan hata ayıklayıcı sunucu uygulaması başlatabilirsiniz. Kapsayıcı Program Yöneticisi'ni ya da Dosya Yöneticisi başlatma hata ayıklayıcısı'ndaki başlatılan sunucu örneğini kullanması kapsayıcı neden olur.  
  
 Erişim için *proje* özellik sayfaları iletişim kutusu, Çözüm Gezgini'nde projenize sağ tıklayın ve ardından kısayol menüsünden Özellikler'i seçin. Komut satırı bağımsız değişkenleri özelliğini bulmak için yapılandırma özellikleri kategorisini genişletin ve hata ayıklama Sayfası'ı tıklatın.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [COM ve ActiveX hata ayıklaması](../debugger/com-and-activex-debugging.md)