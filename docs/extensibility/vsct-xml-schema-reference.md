---
title: "VSCT XML Şeması Başvurusu | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Visual Studio command table configuration files (VSCT), XML schema
- VSCT XML schema elements
ms.assetid: 49e7efae-e713-4762-a824-96fdaf92cdc9
caps.latest.revision: "14"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 1fc82041f8ab2790c63c271f85d573a3105ab8b0
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
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
  
 [CommandTable öğesi](../extensibility/commandtable-element.md)  
  
 [Extern öğesi](../extensibility/extern-element.md)  
  
 [Öğe dahil](../extensibility/include-element.md)  
  
 [Öğe tanımlayın](../extensibility/define-element.md)  
  
 [Komutları öğesi](../extensibility/commands-element.md)  
  
 [CommandPlacements öğesi](../extensibility/commandplacements-element.md)  
  
 [VisibilityConstraints öğesi](../extensibility/visibilityconstraints-element.md)  
  
 [Taşıyan öğesi](../extensibility/keybindings-element.md)  
  
 [UsedCommands öğesi](../extensibility/usedcommands-element.md)  
  
 [Üst öğesi](../extensibility/parent-element.md)  
  
 [Icon öğesi](../extensibility/icon-element.md)  
  
 [Dizeleri öğesi](../extensibility/strings-element.md)  
  
 [Komut bayrağı öğesi](../extensibility/command-flag-element.md)  
  
 [Simgeler öğesi](../extensibility/symbols-element.md)  
  
 [Koşullu öznitelikler](../extensibility/vsct-xml-schema-conditional-attributes.md)  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Kullanıcı arabirimi öğeleri VSPackages nasıl eklenir](../extensibility/internals/how-vspackages-add-user-interface-elements.md)   
 [Komut içinde VSPackages yönlendirme](../extensibility/internals/command-routing-in-vspackages.md)