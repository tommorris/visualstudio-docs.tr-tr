---
title: "Bir etki alanına özgü dil çözüm şablonu seçme | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.topic: article
helpviewer_keywords:
- Domain-Specific Language Tools, solution templates
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload:
- multiple
ms.technology: vs-ide-modeling
ms.openlocfilehash: 0723e5d5e9e2d1d216bdeaf91f1fd2b7752e208c
ms.sourcegitcommit: 205d15f4558315e585c67f33d5335d5b41d0fcea
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/09/2018
---
# <a name="choosing-a-domain-specific-language-solution-template"></a>Etki Alanına Özgü Dil Çözümü Şablonu Seçme
Bir etki alanına özgü dil çözüm oluşturmak için etki alanına özgü dil Tasarımcısı Sihirbazı'nda kullanılabilir çözüm şablonlardan birini seçin. Oluşturmak istediğiniz dil en çok benzeyen bir şablon seçerek başlangıç çözüme yapmak zorunda değişiklikler en aza indirebilirsiniz.  
  
 Etki alanına özgü dil Tasarımcısı Sihirbazı'nda aşağıdaki çözüm şablonları kullanılabilir.  
  
|Şablon|Özellikler|Açıklama|  
|--------------|--------------|-----------------|  
|Sınıf diyagramları|-Bölme şekiller<br />-Sınıf devralma<br />-İlişki devralma<br />-Şekil devralma<br />-İlişki özellikleri|Etki alanına özgü dil varlıkları ve özelliklere sahip ilişkileri içeriyorsa, bu çözüm şablonu kullanın. Bu şablon UML sınıf diyagramları benzer bir etki alanına özgü dil oluşturur. Temel sınıflar ve arabirimler ilişkilendirme, Genelleştirme ve uygulama ilişkileri birlikte varlıklardır. Bir sınıf veya arabirim öznitelikler listesini içeren bir kutu olarak görünür.|  
|Bileşen diyagramları|-Bağlantı noktaları|Etki alanına özgü dil bileşenler diğer bir deyişle, bir yazılım sistemin bölümleri içeriyorsa, bu çözüm şablonu kullanın. Bu şablon UML Bileşen diyagramları benzer bir etki alanına özgü dil oluşturur. Ana bileşenlerini ve dış bileşenlerinin küçük şekiller olarak görünür bağlantı noktaları varlıklardır.|  
|Görev akış diyagramları|-Görüntü ve geometri şekiller<br />-   *Kulvarları*|İş akışları, durumları veya sıraları, etki alanına özgü dil içeriyorsa, bu çözüm şablonu kullanın. Bu şablon UML etkinlik diyagramları benzer bir etki alanına özgü dil oluşturur. Bir etkinlik ana varlıktır ve etkinlikler arasında bir geçiş ana ilişkidir. Şablon başlangıç durumu, son durumunu ve bir eşitleme çubuğu gibi birkaç diğer öğeleri içerir.|  
|En az bir dil|-Bir sınıf ve Şekil<br />-Bir ilişkisi ve bağlayıcı|Etki alanına özgü dil diğer şablonlar benzemez Bu çözüm şablonu kullanın. Bu şablon, iki sınıf ve temsil edilen bir ilişkisi olan bir etki alanına özgü dil oluşturur **araç** olarak **kutusunu** ve **satır**. Sınıf ve ilişki bir örnek dize özelliğine sahip.|  
|En az WinForm Tasarımcısı|-Küçük bir model.<br />-Modeli görüntüler bir Windows formu.|DSL grafik Tasarımcı yerine bir Windows formunda bağlandı bir uygulama oluşturmak istiyorsanız, bu şablonu kullanın.<br /><br /> Dili için kullanıcı arabirimi olarak görev yapar form Dsl\UI klasöründe bulunur.<br /><br /> Form tasarımcısı açmadan önce projeyi oluşturması gerekir.<br /><br /> Daha fazla bilgi için bkz: [Windows Forms-Based etki alanına özgü dil oluşturma](../modeling/creating-a-windows-forms-based-domain-specific-language.md).|  
|En az WPF Tasarımcısı|-Küçük modeli<br />-Modeli görüntüler bir Windows Presentation Foundation kullanıcı arabirimi|DSL grafik Tasarımcı yerine bir WPF kullanıcı arabirimi bağlandı bir uygulama oluşturmak istiyorsanız, bu şablonu kullanın.<br /><br /> Kullanıcı arabirimi için tasarımcı Dsl\UI klasöründe bulunur.<br /><br /> UI Tasarımcısı açmadan önce projeyi oluşturması gerekir.<br /><br /> Daha fazla bilgi için bkz: [WPF-Based etki alanına özgü dil oluşturma](../modeling/creating-a-wpf-based-domain-specific-language.md).|  
|DSL kitaplığı|-En az kitaplığı|Diğer DSL tanımları aktarılabilen bir kısmi DSL tanımı oluşturmak istiyorsanız bu şablonu kullanın.|  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Etki Alanına Özgü Dil Araçlarına Genel Bakış](../modeling/overview-of-domain-specific-language-tools.md)
