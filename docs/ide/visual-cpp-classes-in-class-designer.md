---
title: "Sınıf tasarımcısında Visual C++ sınıfları | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vs.classdesigner.inheritancelinelabel
helpviewer_keywords: Class Designer [Visual Studio], classes
ms.assetid: 75e56f8c-11ef-42a3-b7ec-3d2cf25c581b
caps.latest.revision: "19"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: b4ba110a67604a24517cac90c4645f118a33e722
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="visual-c-classes-in-class-designer"></a>Sınıf Tasarımcısında Visual C++ Sınıfları
Sınıf Tasarımcısı C++ sınıfları destekler ve C++ sınıfları birden çok devralma ilişkisine sahip olabilir ancak bu, Visual Basic ve Visual C# sınıfı şekiller, aynı şekilde yerel C++ sınıfları visualizes. Daha fazla alan ve yöntemleri sınıfında göstermek veya alanından tasarruf etmek için daraltılabilir sınıfı şekli genişletebilirsiniz.  
  
> [!NOTE]
>  Sınıf Tasarımcısı birleşimler (özel türde bir bellek tahsis sınıfı yalnızca UNION'ın en büyük veri üyesi için gerekli miktardır) desteklemez.  
  
## <a name="simple-inheritance"></a>Basit devralma  
 Birden fazla sınıf bir sınıf diyagramı üzerine sürükleyin ve sınıfları sınıf devralma ilişkisi olan bir ok bunları bağlanır. Taban sınıfı yönünü ok noktaları. Aşağıdaki sınıflar sınıf diyagramında görüntülendiğinde, örneğin, bir ok bunları B'den A: ile işaret eden bağlanır  
  
```  
class A {};  
class B : A {};  
```  
  
 Yalnızca sınıf B sınıf diyagramı sürükleyerek de, sınıf şekli B için sağ tıklatın ve ardından **Göster taban sınıfları**. Bu temel sınıfı görüntüler: A.  
  
## <a name="multiple-inheritance"></a>Birden Çok Devralma  
 Sınıf Tasarımcısı birden çok sınıf devralma ilişkileri görselleştirme destekler. *Birden çok devralma* türetilmiş bir sınıf birden fazla temel sınıf özniteliklerini olduğunda kullanılır. Birden çok devralma örneği aşağıdadır:  
  
```  
class Bird {};  
class Swimmer {};  
class Penguin : public Bird, public Swimmer {};  
```  
  
 Birden fazla sınıf sınıf diyagramı üzerine sürükleyin ve sınıfları birden çok sınıf devralma ilişkisi olan bir ok bunları bağlanır. Temel sınıflar yönünü ok noktaları.  
  
 Bir sınıf şekli sağ tıklatıp **Göster temel sınıflar** seçilen sınıf için temel sınıfları görüntüler.  
  
> [!NOTE]
>  **Türetilmiş sınıfları Göster** komutu C++ kodu için desteklenmiyor. Türetilen sınıflar sınıfı genişletme türü düğümü genişletmek görünümüne giderek görüntüleyebilirsiniz **türetilmiş türler** alt klasör ve sonra bu türlerde sınıf diyagramı üzerine sürükleyerek.  
  
 Birden çok sınıf devralma hakkında daha fazla bilgi için bkz: [birden çok devralma](https://msdn.microsoft.com/en-us/library/6td5yws2.aspx) ve [birden çok taban sınıfları](/cpp/cpp/multiple-base-classes).  
  
## <a name="abstract-classes"></a>Soyut sınıflar  
 Sınıf Tasarımcısı soyut sınıflar ("soyut taban sınıfları" olarak da adlandırılan) destekler. Bunlar, hiçbir zaman örneği, ancak başka sınıfların türetilmesi sınıflarıdır. Bu belgedeki daha önceki "Birden çok devralma" den örnek kullanıldığında, örneği `Bird` bireysel nesne olarak aşağıdaki gibi sınıfı:  
  
```  
int main()  
{  
   Bird sparrow;  
   Bird crow;  
   Bird eagle;  
}  
```  
  
 Ancak, oluşturmak istediğiniz değil `Swimmer` ayrı ayrı nesneler olarak sınıfı. Yalnızca diğer türleri hayvan sınıfları bu sınıftan, örneğin, türetilen istiyorsanız `Penguin`, `Whale`, ve `Fish`. Bu durumda, bildirdiğiniz `Swimmer` sınıfı Özet temel sınıf olarak.  
  
 Soyut bir sınıf bildirmek için kullanabileceğiniz `abstract` anahtar sözcüğü. Özet olarak işaretlenmiş ya da bir Özet sınıfta dahil üyeleri sanal ve soyut sınıftan türeyen sınıflar tarafından uygulanmalıdır.  
  
```  
class Swimmer abstract  
{  
   virtual void swim();  
   void dive();  
};  
```  
  
 Bir sınıf soyut olarak en az bir saf sanal işlev ekleyerek de bildirebilirsiniz:  
  
```  
class Swimmer  
{  
   virtual void swim() = 0;  
   void dive();  
};  
```  
  
 Bu bildirimler sınıf adı bir sınıf diyagramında görüntülediğinizde `Swimmer` ve kendi saf sanal işlev `swim` italik gösterimi ile birlikte bir Özet sınıf şeklinde görüntülenir **soyut sınıf**. Noktalı çizgi kenarlığını olması dışında soyut sınıf türü şekli, normal bir sınıf ile aynı olduğuna dikkat edin.  
  
 Bir soyut taban sınıfından türetilmiş bir sınıf temel sınıf her saf sanal işlevi geçersiz kılmanız gerekir veya türetilmiş bir sınıf örneği oluşturulamıyor. Böylece, örneğin, size türetirseniz bir `Fish` sınıfıyla `Swimmer` sınıfı, `Fish` geçersiz kılmanız gerekir `swim` yöntemi:  
  
```  
class Fish : public Swimmer  
{  
   void swim(int speed);  
};  
  
int main()  
{  
   Fish guppy;  
}  
```  
  
 Bu kod bir sınıf diyagramında görüntülediğinizde, bir devralma satırından Sınıf Tasarımcısı çizer `Fish` için `Swimmer`.  
  
## <a name="anonymous-classes"></a>Anonim sınıfları  
 Sınıf Tasarımcısı anonim sınıflarını destekler. *Anonim sınıf türleri* sınıfları bir tanımlayıcı bildirilir. Bunlar Oluşturucusu veya yıkıcı olamaz, işleve bağımsız değişken olarak geçirilemez ve dönüş değerleri olarak işlevler iade edilemez. Anonim sınıf aşağıdaki örnekteki gibi bir typedef ada sahip bir sınıf adını değiştirmek için kullanabilirsiniz:  
  
```  
typedef struct  
{  
    unsigned x;  
    unsigned y;  
} POINT;  
```  
  
 Yapılar, anonim olarak da gerçekleştirilebilir. Sınıf Tasarımcısı ve ilgili türünü görüntüler olarak aynı yapıları anonim sınıflarını görüntüler. Sınıf Tasarımcısı bildirme ve anonim sınıfları ve yapıları görüntüler, ancak belirttiğiniz etiket adını kullanmaz. Sınıf Görünümü oluşturur adını kullanır. Sınıf Görünümü ve bir öğe olarak Sınıf Tasarımcısı sınıf veya yapı görünür adlı **__unnamed**.  
  
 Anonim sınıfları hakkında daha fazla bilgi için bkz: [anonim sınıf türleri](/cpp/cpp/anonymous-class-types).  
  
## <a name="template-classes"></a>Şablon sınıfları  
 Sınıf Tasarımcısı şablon sınıfları görselleştirme destekler. İç içe geçmiş bildirimler desteklenir. Aşağıdaki tabloda bazı tipik bildirimleri gösterir.  
  
|Kod öğesi|Sınıf Tasarımcısı görünümü|  
|------------------|-------------------------|  
|`template <class T>`<br /><br /> `class A {};`|`A<T>`<br /><br /> Şablon sınıfı|  
|`template <class T, class U>`<br /><br /> `class A {};`|`A<T, U>`<br /><br /> Şablon sınıfı|  
|`template <class T, int i>`<br /><br /> `class A {};`|`A<T, i>`<br /><br /> Şablon sınıfı|  
|`template <class T, template <class K> class U>`<br /><br /> `class A {};`|`A<T, U>`<br /><br /> Şablon sınıfı|  
  
 Aşağıdaki tabloda, kısmi uzmanlığı bazı örnekleri gösterilmektedir.  
  
|Kod öğesi|Sınıf Tasarımcısı görünümü|  
|------------------|-------------------------|  
|`template<class T, class U>`<br /><br /> `class A {};`|`A<T, U>`<br /><br /> Şablon sınıfı|  
|`template<class T>`<br /><br /> `class A<T, T> {};`|`A<T, T>`<br /><br /> Şablon sınıfı|  
|`template <class T>`<br /><br /> `class A<T, int> {};`|`A<T, int>`<br /><br /> Şablon sınıfı|  
|`template <class T1, class T2>`<br /><br /> `class A<T1*, T2*> {};`|`A<T1*, T2*>`<br /><br /> Şablon sınıfı|  
  
 Aşağıdaki tabloda kısmi uzmanlığı devralma bazı örnekler gösterilmektedir.  
  
|Kod öğesi|Sınıf Tasarımcısı görünümü|  
|------------------|-------------------------|  
|`template <class T, class U>`<br /><br /> `class A {};`<br /><br /> `template <class TC>`<br /><br /> `class A<T, int> {};`<br /><br /> `class B : A<int, float>`<br /><br /> `{};`<br /><br /> `class C : A<int, int>`<br /><br /> `{};`|`A<T, U>`<br /><br /> Şablon sınıfı<br /><br /> `B`<br /><br /> örneği<br /><br /> (a sınıfı noktalarına)<br /><br /> `C`<br /><br /> örneği<br /><br /> (a sınıfı noktalarına)|  
  
 Aşağıdaki tabloda, şablon işlevleri kısmi uzmanlığı bazı örnekleri gösterilmektedir.  
  
|Kod öğesi|Sınıf Tasarımcısı görünümü|  
|------------------|-------------------------|  
|`class A`<br /><br /> `{`<br /><br /> `template <class T, class U>`<br /><br /> `void func(T a, U b);`<br /><br /> `template <class T>`<br /><br /> `void func(T a, int b);`<br /><br /> `};`|`A`<br /><br /> FUNC\<T, U > (+ 1 aşırı)|  
|`template <class T1>`<br /><br /> `class A {`<br /><br /> `template <class T2>`<br /><br /> `class B {};`<br /><br /> `};`<br /><br /> `template<> template<>`<br /><br /> `class A<type>::B<type> {};`|`A<T1>`<br /><br /> Şablon sınıfı<br /><br /> `B<T2>`<br /><br /> Şablon sınıfı<br /><br /> (B sınıf A altında içinde barındırılan **iç içe geçmiş türler**)|  
|`template <class T>`<br /><br /> `class C {};`<br /><br /> `class A : C<int> {};`|`A`<br /><br /> örneği<br /><br /> C ->\<int ><br /><br /> `C<T>`<br /><br /> Şablon sınıfı|  
  
 Aşağıdaki tablo bazı örnekler şablon devralma gösterir.  
  
|Kod öğesi|Sınıf Tasarımcısı görünümü|  
|------------------|-------------------------|  
|`template <class T>`<br /><br /> `class C {};`<br /><br /> `template<>`<br /><br /> `class C<int> {`<br /><br /> `class B {};`<br /><br /> `}`<br /><br /> `class A : C<int>::B {};`|`A`<br /><br /> örneği<br /><br /> B -><br /><br /> `C<int>`<br /><br /> örneği<br /><br /> (B altında C sınıfı içinde barındırılan **iç içe geçmiş türler**)<br /><br /> `C<T>`<br /><br /> Şablon sınıfı|  
  
 Aşağıdaki tabloda kurallı özel sınıf bağlantı bazı örnekleri gösterilmektedir.  
  
|Kod öğesi|Sınıf Tasarımcısı görünümü|  
|------------------|-------------------------|  
|`template <class T>`<br /><br /> `class C {};`<br /><br /> `template<>`<br /><br /> `class C<int> {};`<br /><br /> `class A : C<int> {};`<br /><br /> `class D : C<float> {};`|`A`<br /><br /> örneği<br /><br /> C ->\<int ><br /><br /> `C<int>`<br /><br /> örneği<br /><br /> `C<T>`<br /><br /> Şablon sınıfı<br /><br /> `D`<br /><br /> örneği<br /><br /> C ->\<float >|  
|`class B {`<br /><br /> `template <class T>`<br /><br /> `T min (const T &a, const T &b);`<br /><br /> `};`|`B`<br /><br /> Min \<T >|  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Visual C++ kodu (Sınıf Tasarımcısı) ile çalışma](../ide/working-with-visual-cpp-code-class-designer.md)   
 [Sınıflar ve yapılar](/cpp/cpp/classes-and-structs-cpp)   
 [Anonim sınıf türleri](/cpp/cpp/anonymous-class-types)   
 [Birden çok devralma](https://msdn.microsoft.com/en-us/library/6td5yws2.aspx)   
 [Birden çok taban sınıfı](/cpp/cpp/multiple-base-classes)   
 [Şablonları](/cpp/cpp/templates-cpp)