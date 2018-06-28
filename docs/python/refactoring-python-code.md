---
title: Python kodu yeniden düzenleme
description: Nasıl kolayca düzenleme yöntemleri, ayıklama tanımlayıcıları yeniden adlandırarak Visual Studio'da Python kodu içeri aktarmalar ekleme ve kullanılmayan kaldırma içeri aktarır.
ms.date: 06/26/2018
ms.prod: visual-studio-dev15
ms.technology: vs-python
ms.topic: conceptual
author: kraigb
ms.author: kraigb
manager: douge
ms.workload:
- python
- data-science
ms.openlocfilehash: c756e92b6abc383cb4515a628fb81308e21a1f01
ms.sourcegitcommit: 0bf2aff6abe485e3fe940f5344a62a885ad7f44e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/27/2018
ms.locfileid: "37056546"
---
# <a name="refactoring-python-code"></a>Python kodu yeniden düzenleme

Visual Studio otomatik olarak dönüştürmek ve Python kaynak kodunuzu Temizleme için çeşitli komutlar sağlamaktadır:

- [Yeniden Adlandır](#rename) seçili sınıfı, yöntemi veya değişken adı yeniden adlandırır
- [Ayıklama yöntemi](#extract-method) yeni bir yöntem seçili kodundan oluşturur
- [İçeri aktarma eklemek](#add-import) eksik alma eklemek için bir akıllı etiket sağlar
- [Kullanılmayan içeri aktarmalar kaldırmak](#remove-unused-imports) kullanılmayan içeri aktarmalar kaldırır

< a name = "rename-variable"</a>

## <a name="rename"></a>Rename

1. Seçin ve yeniden adlandırmak istediğiniz tanımlayıcı sağ tıklayın **yeniden adlandırmak**, bu tanıtıcıyı düzeltme işareti yerleştirin veya seçin **Düzenle > yeniden düzenlemeniz > yeniden adlandırmak...**  menü komutu (F2).
1. İçinde **yeniden adlandırma** görünür, iletişim seçin ve tanımlayıcı için yeni bir ad girin **Tamam**:

  ![Yeni bir tanımlayıcı ad sor yeniden adlandırma](media/code-refactor-rename-1.png)

1. Sonraki iletişim kutusunda, dosya ve kodunuzu uygulanacağı yeniden adlandırma durumlarda seçin; belirli değişikliği önizlemek için tek tek örnek seçin:

  ![Değişiklikleri uygulamak yeri seçmek için iletişim yeniden adlandırma](media/code-refactor-rename-2.png)

1. Seçin **Uygula** , kaynak kodu dosyaları için değişiklik yapma. (Bu işlem geri alınabilir.)

## <a name="extract-method"></a>Ayıklama metodu

1. Kod ya da ayrı bir yöntem ayıklamak için ifade satırları seçin.
1. Seçin **Düzenle > yeniden düzenlemeniz > ayıklamak yöntemi...**  menü komutunu veya türü Ctrl-R, M.
1. Görüntülenen iletişim kutusunda, yeni bir yöntem adını girin, kendisine ayıklamak ve hiçbir Kapatılmak üzere değişken seçin yeri gösterir. Kapatılmak üzere seçilmedi değişkenleri yöntemi bağımsız değişkenleriyle etkinleştirilir:

  ![Yöntem iletişim Ayıkla](media/code-refactor-extract-method-1.png)

1. Seçin **Tamam** ve kodu buna göre değiştirilebilir:

  ![Bir yöntem ayıklanıyor etkisi](media/code-refactor-extract-method-2.png)

## <a name="add-import"></a>İçeri aktarma ekleme

Oturumda bilgileri yazın tanımlayıcıyı şapka yerleştirdiğinizde, Visual Studio komutlarının eklemek gerekli akıllı etiket (ampul simgesi kodun soluna) sağlar `import` veya `from ... import` deyimi:

![İçeri aktarma akıllı etiket ekleme](media/code-refactor-add-import-1.png)

Visual Studio sunar `import` tamamlamalar en üst düzey paketler ve geçerli projeye ve standart kitaplığı modülleri için. Visual Studio sunduğu `from ... import` tamamlamalar modülü üyeleri yanı sıra submodules ve subpackages. Tamamlamalar İşlevler, sınıfları veya dışarı aktarılan verileri içerir. Her iki seçeneğin ekler ifadesine dosyanın üst kısmında diğer içeri aktarmalar sonra ya da mevcut bir uygulamasına `from ... import` aynı modülünün zaten içe aktardıysanız deyimi.

![Sonuç alma ekleme](media/code-refactor-add-import-2.png)

Başka bir dosyaya alınır ancak alma yapılması modülü alt bulunmayan modülleri gibi bir modüldeki gerçekte tanımlı olmayan üyeler filtrelemek Visual Studio çalışır. Örneğin, birçok modül kullanmak `import sys` yerine `from xyz import sys`, içeri aktarma tamamlama görmek istemediğiniz `sys` modülleri eksik olsa bile diğer modüllerden bir `__all__` dışlar üye `sys`.

Benzer şekilde, Visual Studio diğer modüller ya da yerleşik ad alanı içe işlevler filtreler. Örneğin bir modülü içeri aktarır `settrace` işlevini `sys` sonra aldığınız, o modülünden teorik modülü. Ancak kullanmak en iyisidir `import settrace from sys` doğrudan ve Visual Studio bu deyim özellikle sunar.

Son olarak, bir şey normalde dışlanan ancak diğer (adı modülünde bir değer örneğin atandığından), dahil olacak değerleri, Visual Studio hala sahip alma dışlar. Bu davranış değeri başka bir modülde tanımlanır ve böylece ek ataması da aktarılmaz bir kukla değer olması olasıdır çünkü dışarı döndürmemelidir olduğunu varsayar.

< a name = "remove-imports"</a>

## <a name="remove-unused-imports"></a>Kullanılmayan içeri aktarmalar Kaldır

Kod yazarken şunun daha kolaydır `import` deyimleri hiç kullanılmayan modüller. Visual Studio kodunuzun analiz için otomatik olarak belirleyebilirsiniz olup bir `import` deyimi, içeri aktarılan ad deyim oluştuğu kapsamı içinde aşağıdaki mı kullanıldığına bakarak gereklidir.

Herhangi bir yere Düzenleyicisi ve seçin, sağ **kaldırmak içeri aktarmalar**, hangi size kaldırmak için seçenekleri **tüm kapsamlar** veya yalnızca **geçerli kapsam**:

![İçeri aktarmalar menüsü Kaldır](media/code-refactor-remove-imports-1.png)

Visual Studio, ardından koda uygun değişiklikleri yapar:

![İçeri aktarmalar kaldırmanın etkisi](media/code-refactor-remove-imports-2.png)

Visual Studio için denetim akışı hesaplamaz unutmayın; önce bir adı kullanarak bir `import` deyimi, adı aslında kullanıldıysa olarak değerlendirilir. Visual Studio ayrıca yoksayar tüm `from __future__` içeri aktarmalar, bir sınıf tanımı içinde de gelen gerçekleştirilen içeri aktarmalar `from ... import *` deyimleri.