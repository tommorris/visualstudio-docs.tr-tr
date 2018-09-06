---
title: 'Nasıl yapılır: Etki Alanına Özgü bir Dilin Ad Alanını Değiştirme'
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- Domain-Specific Language, namespace
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.prod: visual-studio-dev15
ms.technology: vs-ide-modeling
ms.openlocfilehash: a237664a30dacf351edc048c82d8c9cdc304aa45
ms.sourcegitcommit: 6944ceb7193d410a2a913ecee6f40c6e87e8a54b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/05/2018
ms.locfileid: "43775896"
---
# <a name="how-to-change-the-namespace-of-a-domain-specific-language"></a>Nasıl yapılır: Etki Alanına Özgü bir Dilin Ad Alanını Değiştirme
Etki alanına özgü bir dilin ad alanını değiştirebilirsiniz. Değişiklik yapmanız gereken **DSL Gezgini**, Dsl paket proje özelliklerinde ve derleme bilgileri.

### <a name="to-change-the-namespace-of-a-domain-specific-language"></a>Etki alanına özgü bir dilin ad alanını değiştirmek için

1.  İçinde **DSL Gezgini**, tıklayın **Dsl** düğümü.

2.  İçinde **özellikleri** penceresinde değişiklik **Namespace** özelliği.

3.  Çözüm kaydedin ve şablonlarını Dönüştür.

4.  Üzerinde **proje** menüsünü tıklatın **Dsl özellikleri**.

     Projeniz için Özellikler görünür.

5.  Tıklayın **uygulama** sekmesi.

6.  Değişiklik **varsayılan ad alanı** özelliğini yeni ad alanı adı.

7.  Derlemenin adı değiştirmek istiyorsanız, değişiklik **bütünleştirilmiş kodun ad özelliği.**

8.  Derleme adı değişmişse DslPackage\Package.tt açın ve bu satırı güncelleştirin:

     `string dslAssembly = "YourDSLassembly.Dsl.dll";`

9. Herhangi bir özel kod yazdığınız, kod dosyalarında ad alanını ve sınıf başvuruları değiştirdiğinizden emin olun.

10. Visual Studio deneysel örneği sıfırlayın.

    1.  Silme **\Users\\**_{adınız}_**\AppData\Local\Microsoft\VisualStudio\\\*üs**

    2.  Windows üzerinde **Başlat** menüsünde seçin **tüm programlar**, **Microsoft Visual Studio 2010 SDK**, **Araçları**, **Sıfırla Deneysel örneği**.

11. Üzerinde **derleme** menüsünde seçin **çözümü yeniden derle**.

## <a name="see-also"></a>Ayrıca bkz.

- [Etki alanına özgü dil araçları sözlüğü](http://msdn.microsoft.com/ca5e84cb-a315-465c-be24-76aa3df276aa)