---
title: "Kaynak Denetim eklentisi sözlüğü | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- glossary [Visual Studio SDK]
- source control plug-ins, glossary
ms.assetid: f224bbc9-38fc-4c80-ab09-51dcc8969f8e
caps.latest.revision: "11"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: dc45c47f47fe18bc857715acc3948561f06e718c
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="source-control-plug-in-glossary"></a>Kaynak Denetim eklentisi sözlüğü
Aşağıdaki yararlı terimleri ve tanımları için kaynak denetimi eklentisi SDK Belgeleri ilgilidir.  
  
## <a name="definitions"></a>Tanımlar  
 İade etme  
 Bir kullanıcı çalışma kopyasını değişiklik yaptığında, bir kullanıcı merkezi kaynak denetimi depoya çalışma kopyadan değişiklikleri göndermeniz gerekir. Bu, diğer kullanıcılar için kullanılabilir olan dosya yeni bir sürümünü oluşturur. Bu işlem bir iade etme adı verilir.  
  
 Kullanıma alma  
 Çalışma kopyası üzerinde değişiklik yapma deposu bildiren depodan isteme işlemi. Çalışma kopyası kullanıma andan itibaren proje durumunu yansıtır.  
  
 İstemci  
 Kaynak kodu denetim sistemi kullanan bir programı. Bu belgede, bu Visual Studio IDE olur.  
  
 Yorum  
 Kaynak Denetim işlemi gerçekleştirildiğinde, bir kullanıcı için bir düzeltme iliştirebilirsiniz değişiklikleri açıklayan bir ileti.  
  
 Çakışma  
 İki kullanıcı aynı dosyanın aynı bölgede yapılan değişiklikleri denetlemeye çalıştığınızda bir durumdur. Genellikle, bir birleştirme gerçekleştirilmelidir.  
  
 Dizin  
 İstemci-tarafı yerel bir klasöre dizin olarak adlandırılır. Bu, bir kullanıcı değişiklikleri gerçekten yapar kopyasıdır. Belirli bir projenin birçok çalışma kopyalarını olabilir; genellikle her geliştirici, kendi kopya sahiptir.  
  
 Al  
 Alma işlemi kullanıcının çalışma kopyası güncel depo kopya getirir. Kullanıcı yalnızca en son kopyasını gerekiyor ancak değişiklik amaçlayan bir checkout, bir get gerçekleştirilir.  
  
 Geçmiş  
 Genellikle, bir özeti tüm kullanıma, köprülü, güncelleştirmeler, etiketler ve kaynak denetimi depoya bitti sürümleri yer almaktadır.  
  
 IDE  
 Genelde Visual Studio tümleşik geliştirme ortamına anlamına gelir. Ancak, kaynak denetim eklentisi API tanıması diğer istemci ortamlar da başvurabileceğiniz.  
  
 Birleştir  
 İşlem sırasında iki veya daha fazla kaynak kodu dosyaları önceki dosyalarından tüm özellikleri içeren yeni bir dosya oluşturmak için birleştirilir. Bu kavram burada iki veya daha fazla geliştiriciler dosyalar üzerinde aynı anda çalışması sürüm denetimindeki önemlidir.  
  
 Project  
 Kaynak denetimi klasörü, genellikle bir proje olarak da adlandırılır. Visual Studio'da bu projeleri veya çözümleri ile herhangi bir ilişki yok.  
  
 eklentisi  
 Kaynak Denetim eklentisi API uygulayarak kaynak denetimi işlevsellik sağlar DLL.  
  
 Depo  
 Burada bir kaynak denetim sistem ana kopya bir projenin tam düzeltme geçmişi saklar. Her proje tam olarak bir havuz vardır.  
  
 Gözden geçirme  
 Kaydedilmiş bir değişiklik geçmişini bir dosyanın veya dosya kümesi. Bir düzeltme biridir sürekli olarak değişen bir projede anlık görüntüsünü alın.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Kaynak Denetim Eklentileri](../extensibility/source-control-plug-ins.md)