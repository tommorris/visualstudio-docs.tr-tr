---
title: Python kodu biçimlendirme
description: Aralık, deyimleri, sarmalama ve açıklamalar dahil olmak üzere Visual Studio'da Python kodu otomatik olarak yeniden biçimlendirmek nasıl.
ms.custom: ''
ms.date: 07/12/2017
ms.technology:
- devlang-python
dev_langs:
- python
ms.topic: conceptual
author: kraigb
ms.author: kraigb
manager: douge
ms.workload:
- python
- data-science
ms.openlocfilehash: bd6264c42d8bd4f585d4166fa7cc46b621aa52cc
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="formatting-python-code"></a>Python kodu biçimlendirme

Visual Studio önceden yapılandırılmış biçimlendirme seçeneklerini eşleştirmek için hızlı yeniden biçimlendirme kodu sağlar.

- Bir seçim biçimlendirmek için: seçin **Düzenle > Gelişmiş > Biçim Seçimi** veya Ctrl + E, f tuşlarına basın
- Tüm dosya biçimine: seçin **Düzenle > Gelişmiş > biçimi belge** veya Ctrl + E, d tuşlarına basın

Seçenekler aracılığıyla ayarlanır **Araçlar > Seçenekler > Metin Düzenleyicisi > Python > biçimlendirme** ve iç içe geçmiş sekmelerinin. Seçmenize gerek **tüm ayarları göster** görünmesi Bu seçenekler için:

![Biçimlendirme seçenekleri Visual Studio'da Python](media/options-editor-formatting.png)

Biçimlendirme seçenekleri varsayılan olarak, bir üst eşleşecek şekilde ayarlanır [CESARETLENDİRİCİ 8 Stil Kılavuzu](http://www.python.org/dev/peps/pep-0008/). **Genel** sekmesini belirler zaman biçimlendirme uygulanır; diğer üç sekme ayarlarını, bu makaledeki açıklanmıştır.

[Python desteği Visual Studio'da](installing-python-support-in-visual-studio.md) de yararlı ekler [doldurun açıklama paragraf](#fill-comment-paragraph-command) komutu **Düzenle > Gelişmiş** bir sonraki bölümde açıklandığı gibi menüsü.

## <a name="spacing"></a>Aralığı

**Aralık** burada alanları eklenir veya çeşitli dil yapıları kaldırılan denetimleri. Her bir seçeneğin üç olası değerler vardır:

- Denetleme: aralığı uygulanan sağlar.
- Temizlenmiş: tüm boşlukları kaldırır.
- Belirsiz: özgün biçimlendirme yerinde bırakır.

Örnekler çeşitli seçenekler için aşağıdaki tabloda verilmiştir:

| Sınıf tanımları seçeneği | İşaretli | Temizlenmiş |
| --- | --- | --- | 
| Sınıf bildirimi kişinin adını ve temellerine listeyi arasındaki boşluk Ekle | `class X (object): pass` | `class X(object): pass` | 
| Tabanları listesi parantez içinde boşluk Ekle | `class X( object ): pass` | `class X(object): pass` |
| Boş tabanları listesi parantez içinde boşluk Ekle | `class X( ): pass` | `class X(): pass` |

<br/>

| İşlev tanımları seçeneği | İşaretli | Temizlenmiş |
| --- | --- | --- |
| Bir işlev bildirimi kişinin adı ve parametre listesi arasında boşluk | `def X (): pass` | `def X(): pass` | 
| Parametre listesi parantez içinde boşluk Ekle | `def X( a, b ): pass` | `def X(a, b): pass` |
| Boş parametre listesi parantez içinde boşluk Ekle | `def X( ): pass` | `def X(): pass` |
| Varsayılan parametre değerleri '=' etrafında alanları Ekle | `includes X(a = 42): pass` | `includes X(a=42): pass` |
| Boşluk önce ve sonra dönüş ek açıklama işleçleri | `includes X() -> 42: pass` | `includes X()->42: pass` |

<br/>

| İşleçler seçeneği | İşaretli | Temizlenmiş |
| --- | --- | --- |
| İkili işleçler boşluk Ekle | `a + b` | `a+b` |
| Atamaları boşluk Ekle | `a = b` | `a=b` |

<br/>

| İfade aralığı seçeneği | İşaretli | Temizlenmiş |
| --- | --- | --- |
| İşlev çağrısının kişinin adı ve bağımsız değişken listesi arasında boşluk | `X ()` | `X()` |
| Boş bağımsız değişken listesi parantez içinde boşluk Ekle | `X( )` | `X()` |
| Bağımsız değişken listesi parantez içinde boşluk Ekle | `X( a, b )` | `X(a, b)` |
| Parantez içindeki ifadenin boşluk | `( a )` | `(a)` |
| Boş dizi parantez içinde boşluk Ekle | `( )` | `()` |
| Tuple parantez içinde boşluk Ekle | `( a, b )` | `(a, b)` |
| Boş köşeli ayraçlar içinde boşluk Ekle | `[ ]` | `[]` |
| Köşeli ayraçlar içinde alanları listesi ekleme | `[ a, b ]` | `[a, b]` |
| Açık köşeli ayraç önce boşluk Ekle | `x [i]` | `x[i]` |
| Köşeli ayraçlar içinde boşluk Ekle | `x[ i ]` | `x[i]` |

<br/>

## <a name="statements"></a>Deyimler

**Deyimleri** seçeneklerini denetleme daha fazla Pythonic forms çeşitli deyime otomatik yeniden yazma.

| Seçenek | Biçimlendirme önce | Biçimlendirdikten sonra |
| --- | --- | --- |
| Yeni satırda içe aktarılmış modüllerin yerleştirin | `import sys, pickle` | `import sys`<br/>`import pickle` |
| Gereksiz noktalı Kaldır | `x = 42;` | `x = 42` |
| Birden çok deyime yeni satırlara yerleştirilip yerleştirilmeyeceğini | `x = 42; y = 100` | `x = 42`<br/>`y = 100` |

## <a name="wrapping"></a>Kaydırma

**Kaydırma** ayarladığınız sağlar **en fazla açıklama genişlik** (varsayılan olarak 80). Varsa **sarmalamak çok geniş açıklamalar** seçeneği olarak ayarlanmışsa, Visual Studio, en büyük genişliği aşmayacak şekilde açıklamaları yeniden biçimlendirir.

```python
# Wrapped to 40 columns
# There should be one-- and preferably
# only one --obvious way to do it.
```

```python
# Not-wrapped:
# There should be one-- and preferably only one --obvious way to do it.
```

## <a name="fill-comment-paragraph-command"></a>Açıklama paragraf komutu doldurun

**Düzenle > Gelişmiş > Dolgu açıklama paragraf** (Ctrl + E, P) yeniden akış ve biçimleri, kısa çizgiler birlikte birleştiren ve uzun olanları çiğnemekten metin açıklama satırı yapın.

Örneğin:

```python
# foo
# bar
# baz
```

yapılan değişiklikler:

```python
# foo bar baz
```

```python
# This is a very long long long long long long long long long long long long long long long long long long long comment
```

yapılan değişiklikler:

```python
# This is a very long long long long long long long long long long long long
# long long long long long long long comment
```
