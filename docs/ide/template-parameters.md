---
title: "Visual Studio Proje ve öğe şablon parametreleri | Microsoft Docs"
ms.custom: 
ms.date: 01/02/2018
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Visual Studio templates, parameters
- template parameters [Visual Studio]
- project templates, parameters
- item templates, parameters
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 5e3ce315cd1ddff9445c72f7299a8d6aaf0a3a82
ms.sourcegitcommit: 9357209350167e1eb7e50b483e44893735d90589
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/05/2018
---
# <a name="template-parameters"></a>Şablon parametreleri

Şablon örneği oluşturulduğunda, şablonlarınızı parametreleri kullanarak, sınıf adları ve ad alanları, gibi bir şablon anahtar kısımlarını değerlerini değiştirebilirsiniz. Bu parametre bir kullanıcı seçtiğinde, arka planda çalışan Şablon Sihirbazı tarafından değiştirilir **Tamam** veya **Ekle** içinde **yeni proje** veya **Yeni Öğe Ekle**  iletişim kutuları.

## <a name="declaring-and-enabling-template-parameters"></a>Bildirme ve şablon parametreleri etkinleştirme

Şablon parametreleri biçimi $ bildirilen*parametresi*$. Örneğin:

- $safeprojectname$

- $guid1$

- $guid5$

### <a name="to-enable-parameter-substitution-in-templates"></a>Parametre değiştirme şablonlarındaki etkinleştirmek için

1. Şablon .vstemplate dosyasında bulun `ProjectItem` parametre değiştirme etkinleştirmek istediğiniz öğesine karşılık gelen öğe.

1. Ayarlama `ReplaceParameters` özniteliği `ProjectItem` öğesine `true`.

1. Proje öğesi için kod dosyasında, uygun olan yerlerde parametreleri içerir. Örneğin, aşağıdaki parametre güvenli proje adı ad alanında bir dosya için kullanılabilecek belirtir:

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
|webnamespace|Geçerli Web sitesinin adı. Bu parametre, Web form şablonunda benzersiz sınıf isimleri güvence altına almak için kullanılır. Web sitesi ve Web sunucusunun kök dizininde ise, bu şablon parametresi Web sunucusunun kök dizinine çözümler.|
|Yıl|YYYY biçiminde geçerli yıl.|

> [!NOTE]
> Şablon parametreleri büyük/küçük harfe duyarlıdır.

## <a name="custom-template-parameters"></a>Özel şablon parametreleri

Kendi şablon parametreleri ve parametre değiştirme sırasında kullanılan ayrılmış varsayılan şablon parametreleri ek değerler belirtebilirsiniz. Daha fazla bilgi için bkz: [CustomParameters öğesi (Visual Studio şablonları)](../extensibility/customparameters-element-visual-studio-templates.md).

## <a name="example-using-the-project-name-for-a-file-name"></a>Örnek: Proje adı bir dosya adı için kullanma

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

## <a name="example-using-the-safe-project-name-for-the-namespace-name"></a>Örnek: ad alanı adı için güvenli proje adı kullanma

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

Proje şablonu .vstemplate dosyasına eklenecek `ReplaceParameters="true"` özniteliği dosyasına başvurduğunuzda:

```xml
<TemplateContent>
    <ProjectItem ReplaceParameters="true">
        Class1.cs
    </ProjectItem>
    ...
</TemplateContent>
```

## <a name="see-also"></a>Ayrıca bkz.

[Şablonlarını özelleştirme](../ide/customizing-project-and-item-templates.md)  
[Nasıl yapılır: Proje şablonları oluşturma](../ide/how-to-create-project-templates.md)