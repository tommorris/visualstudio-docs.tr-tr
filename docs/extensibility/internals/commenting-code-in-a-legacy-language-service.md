---
title: Eski dil hizmeti yorum kodda | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- comments, supporting in language services [managed package framework]
- language services [managed package framework], commenting code
ms.assetid: 9600d6f0-e2b6-4fe0-b935-fb32affb97a4
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 5b573b464c26c3864cece697191cf03545ada779
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
ms.locfileid: "31128726"
---
# <a name="commenting-code-in-a-legacy-language-service"></a>Eski dil hizmeti yorum oluşturma kodu
Programlama dilleri, genellikle açıklama eklemek veya kod açıklama olanağı sağlar. Kod hakkında ek bilgi sağlar, ancak derleme veya yorumlama sırasında yok sayılır metnin bir bölümünü bir açıklamadır.  
  
 Yönetilen paket framework (MPF) sınıfları için yorum oluşturma ve uncommenting seçili metni destek sağlar.  
  
## <a name="comment-styles"></a>Açıklama stilleri  
 Açıklama iki genel türlerde vardır:  
  
1.  Açıklama tek bir satıra olduğu satır yorumlar.  
  
2.  Bloğu açıklamaları, birden çok satır yorum burada içerebilir.  
  
 Satır yorumlar genellikle bir başlangıç karakteri (veya karakter), bloğu açıklamaları sırasında başlangıç ve bitiş karakterlerini sahip vardır. Örneğin, C# ' ta satır yorum ile başlayan / /, ve bir blok yorum ile başlayan / * ve ile biten \*/.  
  
 Kullanıcı komut seçtiğinde **Açıklama Seçimi** gelen **Düzenle** -> **Gelişmiş** menüsünde komutu için yönlendirilir <xref:Microsoft.VisualStudio.Package.Source.CommentSpan%2A> yöntemi <xref:Microsoft.VisualStudio.Package.Source> sınıfı. Kullanıcı komut seçtiğinde **açıklamadan çıkarın seçimi**, komut yönlendirilir <xref:Microsoft.VisualStudio.Package.Source.UncommentSpan%2A> yöntemi.  
  
## <a name="supporting-code-comments"></a>Kod açıklamaları destekleme  
 Dil hizmeti destek kodu yorumlarınızı yoluyla olabilir `EnableCommenting` parametresinin adlı <xref:Microsoft.VisualStudio.Shell.ProvideLanguageServiceAttribute> . Bu ayarlar <xref:Microsoft.VisualStudio.Package.LanguagePreferences.EnableCommenting%2A> özelliği <xref:Microsoft.VisualStudio.Package.LanguagePreferences> sınıfı. Dil servicce özellikleri ayarlama hakkında daha fazla bilgi için bkz: [eski dil hizmeti kaydetme](../../extensibility/internals/registering-a-legacy-language-service1.md)).  
  
 Ayrıca geçersiz kılmanız gerekir <xref:Microsoft.VisualStudio.Package.Source.GetCommentFormat%2A> döndürülecek yöntemi bir <xref:Microsoft.VisualStudio.Package.CommentInfo> diliniz için açıklama karakterlerle yapısı. C#-stil satır yorum karakterlerdir, varsayılan değer.  
  
### <a name="example"></a>Örnek  
 Örnek uygulaması işte <xref:Microsoft.VisualStudio.Package.Source.GetCommentFormat%2A> yöntemi.  
  
```csharp  
using Microsoft.VisualStudio.Package;  
  
namespace MyLanguagePackage  
{  
    class MySource : Source  
    {  
        public override CommentInfo GetCommentFormat() {  
            CommentInfo info = new CommentInfo();  
            info.LineStart       = "//";  
            info.BlockStart      = "/*";  
            info.BlockEnd        = "*/";  
            info.UseLineComments = true;  
            return info;  
        }  
    }  
}  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Eski dil hizmeti özellikleri](../../extensibility/internals/legacy-language-service-features1.md)   
 [Eski dil hizmeti kaydetme](../../extensibility/internals/registering-a-legacy-language-service1.md)