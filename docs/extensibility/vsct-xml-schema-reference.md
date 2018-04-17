---
title: VSCT XML Şeması Başvurusu | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- Visual Studio command table configuration files (VSCT), XML schema
- VSCT XML schema elements
ms.assetid: 49e7efae-e713-4762-a824-96fdaf92cdc9
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: e8b8b796f4b5740f90a8755bdf158735387eaa90
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="vsct-xml-schema-reference"></a>VSCT XML Şeması Başvurusu
Komut tablo derleyici şema öğeleri, tablosu ile izin verilen alt öğeleri ve özniteliklerinin her biri için sağlar.  
  
 Bir XML tabanlı komut tablo yapılandırma (.vsct) dosyası bir VSPackage sağlar komutu öğeleri tümleşik geliştirme ortamı (IDE) tanımlar. Menü öğeleri, menüler, araç çubukları ve birleşik giriş kutuları bu öğeler içerir.  
  
> [!NOTE]
>  VSCT derleyici bir önişlemci .vsct dosyasını çalıştırabilirsiniz. Bu genellikle olduğundan C++ dosyalarında kullanılan aynı sözdizimini sahip makroları ve C++ önişlemci tanımlayabileceğiniz içerir. Bu örnekleri .vsct sağlanan dosya **yeni proje** Sihirbazı için bir VSPackage projesi oluşturur.  
  
## <a name="optional-elements"></a>İsteğe bağlı öğeleri  
 Bazı VSCT öğeler isteğe bağlıdır. Varsa bir `Parent` bağımsız değişken belirtilmezse, Group_Undefined:0 kapsanan. Varsa bir `Icon` bağımsız değişken belirtilmezse, guidOfficeIcon:msotcidNoIcon kapsanan. Bir kısayol tuşu tanımlandığında, genellikle kullanılmayan, öykünme isteğe bağlıdır.  
  
 Bit eşlem öğeleri katıştırılmış derleme zamanında bit eşlem şeridinde konumunu belirterek `href` bağımsız değişkeni. Bit eşlem Şerit birleştirme sırasında kopyalanan yerine DLL kaynaklarından ayıklanan. Zaman bir `href` bağımsız değişkeni sağlanır, `usedList` bağımsız değişken isteğe bağlı olur ve bit eşlem Şerit tüm yuvalarında kullanılan olarak kabul edilir.  
  
 Simgesel adları kullanarak tüm GUID ve ID değerleri tanımlanması gerekir. Bu adları üst bilgi dosyaları veya VSCT tanımlanabilir \<simgeleri > bölümler. Sembolik adlar aracılığıyla dahil yerel olmalıdır, \<Ekle > öğeleri veya tarafından başvurulan \<Extern > öğeleri. Belirtilen bir üst bilgi dosyasını bir simgesel ad aktarıldığı bir \<Extern > basit desenini izliyorsa öğesi # SEMBOL değeri define. Bu simgeyi önceden tanımlanmış sürece değeri başka bir simge olabilir. GUID tanımları OLE ya da C++ biçime uymalıdır. KOD değerleri, ondalık sayılar veya 0 x tarafından öncesinde onaltılık basamak aşağıdaki satırlarda gösterildiği gibi olabilir:  
  
-   {6D484634-E53D-4a2c-ADCB-55145C9362C8}  
  
-   {0x6d484634, 0xe53d, 0x4a2c, {0xad, 0xcb, 0x55, 0x14, 0x5c, 0x93, 0x62, 0xc8}}  
  
 XML açıklamaları kullanılabilir, ancak gidiş dönüş grafik kullanıcı arabirimi (GUI) araçları atmak. İçeriğini \<ek açıklama > öğeleri biçimi ne olursa olsun korunmasını garanti edilir.  
  
## <a name="schema-hierarchy"></a>Şema hiyerarşisi  
 .Vsct dosyasında aşağıdaki temel öğe var.  
  
 [CommandTable Öğesi](../extensibility/commandtable-element.md)  
  
 [Extern Öğesi](../extensibility/extern-element.md)  
  
 [Include Öğesi](../extensibility/include-element.md)  
  
 [Define Öğesi](../extensibility/define-element.md)  
  
 [Commands Öğesi](../extensibility/commands-element.md)  
  
 [CommandPlacements Öğesi](../extensibility/commandplacements-element.md)  
  
 [VisibilityConstraints Öğesi](../extensibility/visibilityconstraints-element.md)  
  
 [KeyBindings Öğesi](../extensibility/keybindings-element.md)  
  
 [UsedCommands Öğesi](../extensibility/usedcommands-element.md)  
  
 [Parent Öğesi](../extensibility/parent-element.md)  
  
 [Icon Öğesi](../extensibility/icon-element.md)  
  
 [Strings Öğesi](../extensibility/strings-element.md)  
  
 [Command Flag Öğesi](../extensibility/command-flag-element.md)  
  
 [Symbols Öğesi](../extensibility/symbols-element.md)  
  
 [Koşullu öznitelikler](../extensibility/vsct-xml-schema-conditional-attributes.md)  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Kullanıcı arabirimi öğeleri VSPackages nasıl eklenir](../extensibility/internals/how-vspackages-add-user-interface-elements.md)   
 [VSPackage’larda Komut Yönlendirme](../extensibility/internals/command-routing-in-vspackages.md)