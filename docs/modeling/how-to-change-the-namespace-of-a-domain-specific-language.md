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
ms.openlocfilehash: 1963502f3940fd0d17c770f111e07de14207e687
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/26/2018
ms.locfileid: "31948268"
---
# <a name="how-to-change-the-namespace-of-a-domain-specific-language"></a>Nasıl yapılır: Etki Alanına Özgü bir Dilin Ad Alanını Değiştirme
Bir etki alanına özgü dil ad alanı değiştirebilirsiniz. Değişiklik yapmanız gereken **DSL Explorer**, Dsl paket proje özelliklerini ve derleme bilgileri.

### <a name="to-change-the-namespace-of-a-domain-specific-language"></a>Bir etki alanına özgü dil ad alanı değiştirmek için

1.  İçinde **DSL Explorer**, tıklatın **Dsl** düğümü.

2.  İçinde **özellikleri** penceresinde, değişiklik **Namespace** özelliği.

3.  Çözüm kaydedin ve şablonları dönüştürme.

4.  Üzerinde **proje** menüsünde tıklatın **Dsl özellikleri**.

     Projeniz için Özellikler görünür.

5.  Tıklatın **uygulama** sekmesi.

6.  Değişiklik **varsayılan ad alanı** özelliği için yeni ad alanı adı.

7.  Ayrıca derlemenin adını değiştirmek isterseniz, değiştirmek **derleme name özelliği.**

8.  Derleme adı değişirse, DslPackage\Package.tt açın ve bu satırı güncelleştirin:

     `string dslAssembly = "YourDSLassembly.Dsl.dll";`

9. Özel kod yazdıysanız, ad alanını ve sınıf başvurularını kod dosyalarında değiştirdiğinizden emin olun.

10. Visual Studio deneysel örneği sıfırlayın.

    1.  Silme **\Users\\ ***{ad}*** \AppData\Local\Microsoft\VisualStudio\\\*Exp**

    2.  Windows **Başlat** menüsünde seçin **tüm programlar**, **Microsoft Visual Studio 2010 SDK**, **Araçları**, **Sıfırla Deneysel örneği**.

11. Üzerinde **yapı** menüsünde seçin **çözümü yeniden derle**.

## <a name="see-also"></a>Ayrıca bkz.

- [Etki alanına özgü dil araçları sözlüğü](http://msdn.microsoft.com/ca5e84cb-a315-465c-be24-76aa3df276aa)