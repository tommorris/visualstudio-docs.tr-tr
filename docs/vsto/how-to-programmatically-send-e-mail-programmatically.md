---
title: 'Nasıl yapılır: program aracılığıyla e-posta gönderme | Microsoft Docs'
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- mail items [Office development in Visual Studio], sending e-mail
- Outlook [Office development in Visual Studio], creating e-mail
- Outlook [Office development in Visual Studio], sending e-mail
- e-mail [Office development in Visual Studio], sending
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: c3ee656a8a4965f01969bad19d66d0ea6215bcbe
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="how-to-programmatically-send-e-mail"></a>Nasıl yapılır: program aracılığıyla e-posta Gönder  
  Bu örnekte, etki alanı adına sahip kişiler için bir e-posta iletisi gönderilir **example.com** e-posta adreslerini içinde.  
  
 [!INCLUDE[appliesto_olkallapp](../vsto/includes/appliesto-olkallapp-md.md)]  
  
## <a name="example"></a>Örnek  
 [!code-csharp[Trin_OL_ProgramEmail#1](../vsto/codesnippet/CSharp/Trin_OL_ProgramEMail/thisaddin.cs#1)]  
  
## <a name="compiling-the-code"></a>Kod Derleniyor  
 Bu örnek gerektirir:  
  
-   Etki alanı adına sahip kişiler **example.com** e-posta adreslerini içinde.  
  
## <a name="robust-programming"></a>Güçlü Programlama  
 Etki alanı adını arar filtre kodunu kaldırmayın **example.com**. Filtre kaldırırsanız çözümünüzü tüm kişilerinizin e-posta iletileri gönderir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Posta öğeleri ile çalışma](../vsto/working-with-mail-items.md)   
 [Nasıl yapılır: program aracılığıyla e-posta öğesi oluşturma](../vsto/how-to-programmatically-create-an-e-mail-item.md)   
 [Nasıl yapılır: program aracılığıyla, Outlook Kişilerine erişme](../vsto/how-to-programmatically-access-outlook-contacts.md)   
 [Nasıl yapılır: E-Posta İletisi Alındığında Program Aracılığıyla İşlem Gerçekleştirme](../vsto/how-to-programmatically-perform-actions-when-an-e-mail-message-is-received.md)  
  
  