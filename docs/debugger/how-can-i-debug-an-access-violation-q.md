---
title: C++ erişim ihlali nasıl hata Ayıklayabilirim? | Microsoft Docs
ms.custom: ''
ms.date: 05/23/2017
ms.technology: vs-ide-debug
ms.topic: conceptual
f1_keywords:
- vs.debug.access
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords:
- access violation debugging
- debugging [Visual Studio], access violations
ms.assetid: 9311d754-0ce9-4145-b147-88b6ca77ba63
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- cplusplus
ms.openlocfilehash: b131ba4acf761a11aa9f39807d1db3202b021c9d
ms.sourcegitcommit: 3d10b93eb5b326639f3e5c19b9e6a8d1ba078de1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/18/2018
---
# <a name="how-can-i-debug-a-c-access-violation"></a>C++ erişim ihlali nasıl hata Ayıklayabilirim?
## <a name="problem-description"></a>Sorun açıklaması  
 Kendi programımı bir erişim ihlali üretir. Bu nasıl hata ayıklayabilirim?  
  
## <a name="solution"></a>Çözüm  
 Birden çok işaretçileri dereferences kod satırında bir erişim ihlali alırsanız, hangi işaretçi erişim ihlali neden olduğunu bulmak zor olabilir. Visual Studio 2015 güncelleştirme 1'de başlayarak, özel durum iletişim kutusu artık açıkça erişim ihlali neden işaretçi olarak adlandırır.  
  
 Örneğin, aşağıdaki kod verildiğinde, erişim ihlali almanız gerekir:  
  
```C++  
#include <iostream>  
using namespace std;  
  
class ClassB {  
public:  
        ClassC* C;  
        ClassB() {  
                C = new ClassC();  
        }  
     void printHello() {  
                cout << "hello world";  
        }  
};  
  
class ClassA {  
public:  
    ClassB* B;  
      ClassA() {  
                B = nullptr;  
        }  
};  
  
int main() {  
    ClassA* A = new ClassA();  
      A->B->printHello();  
}  
```  
  
 Visual Studio 2015 güncelleştirme 1'de bu kodu çalıştırmak, şu özel durum iletişim kutusu görmeniz gerekir:  
  
 ![AccessViolationCPlus](../debugger/media/accessviolationcplus.png "AccessViolationCPlus")  
  
 İşaretçinin bir erişim ihlali neden neden belirleyemiyorsa, soruna işaretçi doğru atandığından emin olmak için kod boyunca izleme.  Bir parametre olarak geçirilen, doğru şekilde geçirilir ve yanlışlıkla oluşturma olmayan emin olun bir [kopyalama yüzeysel](http://stackoverflow.com/questions/184710/what-is-the-difference-between-a-deep-copy-and-a-shallow-copy). Daha sonra değerleri kasıtsız olarak herhangi bir yerde programa veri kesme noktası işaretçisi, başka bir programa değiştirilen olmadığından emin olmak için söz konusu oluşturarak değiştirilmekte olan değil olduğunu doğrulayın. Veri kesme noktası bölümünde veri kesme noktaları hakkında daha fazla bilgi için bkz: [kullanarak kesme noktaları](../debugger/using-breakpoints.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Yerel kod hata ayıklaması SSS](../debugger/debugging-native-code-faqs.md)