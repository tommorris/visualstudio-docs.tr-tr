---
title: Seçenekler İletişim Kutusu, Projeler ve Çözümler, Derleme ve Çalıştırma
ms.date: 07/14/2017
ms.prod: visual-studio-dev15
ms.technology: vs-ide-general
ms.topic: reference
f1_keywords:
- VS.ToolsOptionsPages.Projects.Build_and_Run
- VS.ToolsOptionsPag.Projects.Build_and_Run
helpviewer_keywords:
- builds [Visual Studio], setting up
- run actions
- debugger, run options
ms.assetid: c884976e-c0df-4c6d-8e3a-856ea2bd547c
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: f6a569162105ffb577bdad854d973fff91b3c81b
ms.sourcegitcommit: ce154aee5b403d5c1c41da42302b896ad3cf8d82
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/07/2018
ms.locfileid: "34845044"
---
# <a name="options-dialog-box-projects-and-solutions-build-and-run"></a>Seçenekler İletişim Kutusu, Projeler ve Çözümler, Derleme ve Çalıştırma

Bu iletişim kutusunda, aynı anda oluşturabilirsiniz Visual C++ veya C# projeleri üst sınırını belirtebilirsiniz, belirli varsayılan davranışlar yapı ve bazı günlük ayarlarını oluşturun. Bu seçenekler erişmek için seçin **Araçlar > Seçenekler** genişletin **projeler ve çözümler**seçip **derleme ve çalıştırma**.

**Yapılar paralel olarak proje maksimum sayısı**

Aynı anda oluşturabilirsiniz Visual C++ ve C# projeleri en fazla sayısını belirtir. Derleme işlemi iyileştirmek için paralel olarak proje derlemeleri sayısı bilgisayarınızın CPU sayısı için otomatik olarak ayarlanır. En fazla 32'dir.

**Başlangıç projeleri ve bağımlılıkları çalıştırılmasında yalnızca derleme**

F5 anahtar, select kullandığınızda yalnızca başlangıç projesi ve onun bağımlılıklarını derlemeler **hata ayıklama > başlangıç** menü komutu ya da geçerli komutlarını **yapı** menüsü. NET, tüm projeleri ve bağımlılıkları yapı demektir.

**Projeleri güncel olduğunda çalıştırılmasında**

*Uygulandığı öğe [!INCLUDE[vcprvc](../../code-quality/includes/vcprvc_md.md)] yalnızca projeleri.*

F5 ile bir proje çalışırken veya **hata ayıklama > başlangıç** komutu, varsayılan ayar **oluşturmak komut istemi** bir proje yapılandırma güncel değil, bir ileti görüntüler. Seçin **her zaman yapı** her çalıştırıldığında Projeyi derlemek için. Seçin **hiçbir zaman yapı** bir projeyi çalıştırdığınızda tüm otomatik derlemeleri gizlemek için.

**Çalıştırmada, ne zaman yapı veya dağıtım hataları oluşuyor**

*Uygulandığı öğe [!INCLUDE[vcprvc](../../code-quality/includes/vcprvc_md.md)] yalnızca projeleri.*

F5 ile bir proje çalışırken veya **hata ayıklama > başlangıç** komutu, varsayılan ayar **başlatmak komut istemi** derleme başarısız olsa bile bir proje çalışması gereken bir ileti görüntüler. Seçin **başlatma eski sürümünü** kod çalıştırırken ve kaynak kodu arasında eşleşmeler sonuçlanabilir son iyi yapılandırma otomatik olarak başlatılacak. Seçin **değil başlatma** iletinin gösterilmemesi için.

**Yeni çözümler için şu anda seçili proje başlangıç projesi olarak kullanın.**

Bu seçenek ayarlandığında, yeni çözümler şu anda seçili proje başlangıç projesi olarak kullanın.

**MSBuild proje derleme çıktı ayrıntı**

Ne kadar bilgi görünür belirler **çıkış** penceresi derleme için.

**MSBuild proje derleme günlük dosyası ayrıntı**

*Uygulandığı öğe [!INCLUDE[vcprvc](../../code-quality/includes/vcprvc_md.md)] yalnızca projeleri.*

Ne kadar bilgi bulunur yapı günlük dosyasına yazılır belirler \\... \\ *ProjectName*\Debug\\*ProjectName*. günlük.

## <a name="see-also"></a>Ayrıca bkz.

- [Derleme ve Oluşturma](../../ide/compiling-and-building-in-visual-studio.md)
- [Seçenekler iletişim kutusu, projeler ve çözümler](projects-and-solutions-options-dialog-box.md)
- [Seçenekler iletişim kutusu, projeler ve çözümler, Web projeleri](options-dialog-box-projects-and-solutions-web-projects.md)