---
title: "Görevler hata ayıklama | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: debugging [Debugging SDK], tasks
ms.assetid: 5d60e9e8-305e-4a48-829f-b9440fc8af7b
caps.latest.revision: "16"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: d1a6ffff4d3ac0410ca3de7e2cd595119763e88b
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="debugging-tasks"></a>Hata ayıklama görevleri
Bir program hata ayıklamak için onu başlatılması gerekir ve hata ayıklama altyapısı (DE) bağlı gerekir, aksi takdirde DE daha önce başlatılan program için'e bağlı olması gerekir. Bağlandıktan sonra DE belirli başlangıç olayları oluşturmanız gerekir. IDE içinde ayarlama kesme noktaları bağlamak hata ayıklama paket yanıt olarak çalışır. Program ilişkili bir kesme noktası geldiğinde durur ve kullanıcı girişi için bekler.  
  
## <a name="in-this-section"></a>Bu Bölümde  
 [Güvenlik Sorunları](../../extensibility/debugger/security-issues.md)  
 Bir program hata ayıklamak için gereken güvenlik adımlar açıklanmaktadır.  
  
 [Program Başlatma](../../extensibility/debugger/launching-a-program.md)  
 Programını başlatmak için işletim sistemi çağırır SE belirtmek adım adım yönergeler verilmektedir.  
  
 [Doğrudan Programa Ekleme](../../extensibility/debugger/attaching-directly-to-a-program.md)  
 Bir programda zaten çalıştırılan bir işlemde hata ayıklamak için kullanılan işlem açıklanır.  
  
 [Başlatmadan Sonra Başlangıç Olaylarını Gönderme](../../extensibility/debugger/sending-startup-events-after-a-launch.md)  
 Program kendi ana giriş noktası ve hata ayıklama için hazır kadar DE programına bağlandıktan sonra gerçekleşecek olayları listeler.  
  
 [Yürütme Denetimi](../../extensibility/debugger/control-of-execution.md)  
 Ne DE genellikle bir giriş noktası olay, bir yük tamamlama olayı veya koşullara bağlı olarak bir durdurma olay gönderir açıklanmaktadır.  
  
 [Kesme Noktaları Bağlama](../../extensibility/debugger/binding-breakpoints.md)  
 Kullanıcı bir kesme noktası ayarlarsa, IDE isteği formulates ve nasıl kesme noktası oluşturmak için hata ayıklama oturumu ister açıklanmaktadır.  
  
 [İfadeleri Değerlendirme](../../extensibility/debugger/evaluating-expressions.md)  
 İfadeleri nasıl oluşturulur ve bir ifade değerlendirildiğinde ne olacağını açıklar.  
  
 [Verileri Görselleştirme ve Görüntüleme](../../extensibility/debugger/visualizing-and-viewing-data.md)  
 Tür görselleştiriciler ve özel görüntüleyicileri ifade değerlendiricisi (EE) nasıl desteklenen açıklanmaktadır.  
  
## <a name="related-sections"></a>İlgili Bölümler  
 [Hata Ayıklayıcı Kavramları](../../extensibility/debugger/debugger-concepts.md)  
 Ana hata ayıklama mimari kavramlarını açıklar.  
  
 [Hata Ayıklayıcı Bileşenleri](../../extensibility/debugger/debugger-components.md)  
 DE, EE ve sembol işleyici (SH) içeren Visual Studio hata ayıklama bileşenlerini genel bir bakış sağlar.  
  
 [Hata Ayıklayıcı Bağlamları](../../extensibility/debugger/debugger-contexts.md)  
 Nasıl DE aynı anda kod, belgeler ve ifade değerlendirme bağlamı içinde çalıştığı açıklanmaktadır. , Her üç bağlamları, konum, konum veya değerlendirme için ilgili açıklar.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Başlarken](../../extensibility/debugger/getting-started-with-debugger-extensibility.md)