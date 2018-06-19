---
title: Visual Studio Proje ve öğe şablon parametreleri
ms.date: 01/02/2018
ms.prod: visual-studio-dev15
ms.technology: vs-ide-general
ms.topic: reference
helpviewer_keywords:
- Visual Studio templates, parameters
- template parameters [Visual Studio]
- project templates, parameters
- item templates, parameters
author: gewarren
ms.author: gewarren
manager: douge
ms.openlocfilehash: abac68ff371040a7f121a885065c8c3eaf9af8ff
ms.sourcegitcommit: 04a717340b4ab4efc82945fbb25dfe58add2ee4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/28/2018
ms.locfileid: "32066540"
---
# <a name="template-parameters"></a>Şablon parametreleri

Şablon örneği oluşturulduğunda şablonunuzda değerlerini değiştirebilirsiniz. Bu işlevini ayarlamak için kullanın *şablon parametreleri*. Şablon parametreleri sınıf adları ve şablon için ad alanları gibi değerleri değiştirmek için kullanılabilir. Şablon Sihirbazı, bir kullanıcı yeni bir öğe ekler veya bu parametreleri proje değiştirir arka planda çalışır.

## <a name="declaring-and-enabling-template-parameters"></a>Bildirme ve şablon parametreleri etkinleştirme

Şablon parametreleri biçimi $ bildirilen*parametresi*$. Örneğin:

- $safeprojectname$

- $guid1$

- $guid5$

### <a name="to-enable-parameter-substitution-in-templates"></a>Parametre değiştirme şablonlarındaki etkinleştirmek için

1. İçinde *.vstemplate* dosya şablonunu, bulun `ProjectItem` parametre değiştirme etkinleştirmek istediğiniz öğesine karşılık gelen öğe.

1. Ayarlama `ReplaceParameters` özniteliği `ProjectItem` öğesine `true`.

1. Proje öğesi için kod dosyasında, uygun olan yerlerde parametreleri içerir. Örneğin, aşağıdaki parametre güvenli proje adı ad alanında bir dosya için kullanıldığını belirtir:

    ```csharp
    namespace $safeprojectname$
    ```

## <a name="reserved-template-parameters"></a>Ayrılmış şablon parametreleri

Aşağıdaki tabloda herhangi bir şablonu tarafından kullanılan ayrılmış şablon parametreleri listeler.

|Parametre|Açıklama|
|---------------|-----------------|
|clrversion|Ortak dil çalışma zamanı (CLR) geçerli sürümü.|
|GUID [1-10]|Bir proje dosyasında GUID proje değiştirmek için kullanılan bir GUID. En fazla 10 benzersiz GUID'ler belirtebilirsiniz (örneğin, `guid1`).|
|ItemName|Kullanıcı tarafından sağlanan adı **Yeni Öğe Ekle** iletişim kutusu.|
|MachineName|Geçerli bilgisayar adı (örneğin, Computer01).|
|ProjectName|Kullanıcı tarafından sağlanan adı **yeni proje** iletişim kutusu.|
|RegisteredOrganization|Kayıt defteri anahtar değeri HKLM\Software\Microsoft\Windows NT\CurrentVersion\RegisteredOrganization.|
|RootNamespace|Kök ad alanı geçerli projenin. Bu parametre yalnızca öğe şablonları için geçerlidir.|
|safeitemname|Kullanıcı tarafından sağlanan adı **Yeni Öğe Ekle** olan tüm güvenli olmayan karakter ve boşlukları kaldırılmış iletişim kutusu.|
|safeprojectname|Kullanıcı tarafından sağlanan adı **yeni proje** olan tüm güvenli olmayan karakter ve boşlukları kaldırılmış iletişim kutusu.|
|zaman|AA/GG/YYYY biçiminde geçerli saat 00:00:00.|
|SpecificSolutionName|Çözüm adı. "Çözüm dizini oluşturma" işaretlendiğinde `SpecificSolutionName` çözüm adına sahip. "Çözüm dizini oluşturma" işaretli olduğunda `SpecificSolutionName` boştur.|
|userdomain|Geçerli kullanıcı etki alanı.|
|Kullanıcı adı|Geçerli kullanıcı adı.|
|webnamespace|Geçerli web sitesinin adı. Bu parametre, web form şablonunda benzersiz sınıf isimleri güvence altına almak için kullanılır. Web sitesi ve web sunucusunun kök dizininde ise, bu şablon parametresi web sunucusunun kök dizinine çözümler.|
|Yıl|YYYY biçiminde geçerli yıl.|

> [!NOTE]
> Şablon parametreleri büyük/küçük harfe duyarlıdır.

## <a name="custom-template-parameters"></a>Özel şablon parametreleri

Kendi şablon parametreleri ve parametre değiştirme sırasında kullanılan ayrılmış varsayılan şablon parametreleri ek değerler belirtebilirsiniz. Daha fazla bilgi için bkz: [CustomParameters öğesi (Visual Studio şablonları)](../extensibility/customparameters-element-visual-studio-templates.md).

## <a name="example-use-the-project-name-for-a-file-name"></a>Örnek: Proje adı bir dosya adı için kullanma

İçindeki bir parametre kullanarak proje öğeleri için değişken dosya adları belirtebilirsiniz `TargetFileName` özniteliği.

Aşağıdaki örnekte bir yürütülebilir dosyanın adı tarafından belirtilen proje adı kullandığını belirtir `$projectname$`.

```xml
<TemplateContent>
    <ProjectItem
        ReplaceParameters="true"
        TargetFileName="$projectname$.exe">
            File1.exe
    </ProjectItem>
      ...
</TemplateContent>
```

## <a name="example-use-the-safe-project-name-for-the-namespace-name"></a>Örnek: ad alanı adı için güvenli proje adı kullanın

C# sınıfı dosyasında ad alanı için güvenli proje adı kullanmak için aşağıdaki sözdizimini kullanın:

```csharp
namespace $safeprojectname$
{
    public class Class1
    {
        public Class1()
        { }
    }
}
```

İçinde *.vstemplate* içeriyor, dosya için proje şablonu `ReplaceParameters="true"` özniteliği dosyasına başvurduğunuzda:

```xml
<TemplateContent>
    <ProjectItem ReplaceParameters="true">
        Class1.cs
    </ProjectItem>
    ...
</TemplateContent>
```

## <a name="see-also"></a>Ayrıca bkz.

- [Şablonları özelleştirme](../ide/customizing-project-and-item-templates.md)
- [Nasıl yapılır: Proje şablonları oluşturma](../ide/how-to-create-project-templates.md)
