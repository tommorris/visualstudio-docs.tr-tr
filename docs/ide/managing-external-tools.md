---
title: "Dış araçları yönetme | Microsoft Docs"
ms.custom: 
ms.date: 02/17/2017
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vs.externaltools
helpviewer_keywords:
- Create GUID tool
- RC (Resource Compiler)
- ReBase tool
- Windows NT Message Compiler
- Windows NT C++ Symbol Undecorator
- tstcon32.exe
- Type Library Generator
- Windows NT Image Binder
- tools [Visual Studio], external
- RowsetViewer tool
- utilities, external tools
- Local Test Manager
- OLE DB Rowset Viewer
- Midlc (IDL Compiler)
- ATL Trace Tool
- Odbcte32w.exe
- IDL Compiler
- HCW (Help Workshop)
- Message Compiler [Visual Studio]
- UUID Generator
- MIDL, external tools
- ErrLook tool
- MAKEHM tool
- Error lookup tool
- OLEVIEW (Object Viewer)
- Uuidgen.exe
- WebDbg tool
- OLE/COM Object Viewer
- LTM (Local Test Manager)
- ATLTraceTool.exe
- Bind tool
- Vsvars32.bat
- external tools [Visual Studio]
- ODBC Test
- Windows NT Image Rebaser
- undname.exe
- Vcspawn.exe
- ActiveX Control Test Container
- mc (Message Compiler)
- GUIDGEN tool
- Odbcte32.exe
- DisableMsg tool
- MkTypLib tool
- Help Workshop
- Resource Compiler
ms.assetid: f382fd40-a98f-4934-8c9a-5aeae881acde
caps.latest.revision: "38"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 9829887a28ec2e672999732e38604f3d9d6fea9a
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="manage-external-tools"></a>Dış araçları yönetme
Dış Araçları'ndan çağırabilirsiniz kullanarak Visual Studio içinde **Araçları** menüsü. Birkaç varsayılan araçları mevcuttur **Araçları** menüsü, ancak diğer yürütülebilir kendi ekleyebilirsiniz.  

## <a name="tools-available-on-the-visual-studio-tools-menu"></a>Visual Studio Araçları menüsünde kullanılabilen Araçlar
 **Araçları** menüsü birkaç yerleşik komutları gibi içerir:

*  **Uzantılar ve güncelleştirmeler** için [Visual Studio uzantılarını yönetme](finding-and-using-visual-studio-extensions.md)
*  **Kod parçacıkları Yöneticisi...**  için [kod parçacıkları düzenleme](code-snippets.md#code-snippet-manager)
*  **PreEmptive tarafından koruması - Dotfuscator** başlatmak için [Dotfuscator Community Edition (CE)](dotfuscator/index.md) , [yüklü](dotfuscator/install.md)
*  **Özelleştir...**  için [menüleri ve araç çubuklarını özelleştirme](how-to-customize-menus-and-toolbars-in-visual-studio.md)
*  **Seçenekler...**  için [çeşitli Visual Studio IDE ve diğer araçları için farklı seçenekleri ayarlama](reference/options-dialog-box-visual-studio.md)

## <a name="add-new-tools-to-the-tools-menu"></a>Araçlar menüsünde yeni araçları ekleme 
 Bir dış aracı ekleyebilirsiniz **Araçları** menüsü. Açık **harici araçlar...**  iletişim kutusu ve tıklatın **Ekle**, bilgileri doldurun. Örneğin, Windows Explorer'ın şu anda dosya dizininde açmak için şu girdiyi Visual Studio'da Aç nedenleri:  
  
1.  Başlık: *dosya konumunu Aç*
  
2.  Komut:`explorer.exe`  
  
3.  Bağımsız değişkenler:`/root, "$(ItemDir)"`  
  
 Bir dış aracı tanımlarken kullanılabilir değişkenlerin tam listesi verilmiştir.
  
> [!NOTE]
>  IDE durum çubuğu ekleme noktasını etkin Kod düzenleyicisinde bulunduğu belirtmek için geçerli satır ve geçerli sütun değişkenlerini görüntüler. Geçerli metin değişkeni metin ya da bu konumda seçili kodu döndürür.  
  
|Ad|Bağımsız Değişken|Açıklama|  
|----------|--------------|-----------------|  
|Öğe yolu|$(ItemPath)|Geçerli dosyasının tam dosya adı (sürücü + yolu + dosya adı).|  
|Öğe dizini|$(ItemDir)|Geçerli bir dosya (sürücü + yolu) dizini.|  
|Öğe dosya adı|$(ItemFilename)|Dosyasının dosya adını geçerli (dosya adı).|  
|Öğe uzantısı|$(ItemExt)|Geçerli dosyanın dosya adı uzantısı.|  
|Geçerli satır|$(CurLine)|İmleç kod penceresinde geçerli satır konumu.|  
|Geçerli sütun|$(CurCol)|İmleç kod penceresinde geçerli sütun konumu.|  
|Geçerli metin|$(CurText)|Seçili metni.|  
|Hedef yolu|$(TargetPath)|Oluşturulacak öğesinin tam dosya adı (sürücü + yolu + dosya adı).|  
|Hedef Dizin|$(TargetDir)|Oluşturulacak öğenin dizini.|  
|Hedef Adı|$(TargetName)|Oluşturulacak öğenin dosya adı.|  
|Hedef uzantısı|$(TargetExt)|Oluşturulacak öğenin dosya adı uzantısı.|  
|İkili dizin|$(BinDir)|Oluşturulmakta olan ikili (sürücü + yolu tanımlanan) son konumu. Örneğin:**\\... \My Documents\Visual Studio \<sürüm >\\< ProjectName\>\bin\debug**|  
|Proje dizini|$(ProjDir)|Geçerli projenin (sürücü + yolu) dizini.|  
|Proje dosyası adı|$(ProjFileName)|Geçerli projenin dosya adı (sürücü + yolu + dosya adı).|  
|Çözüm dizini|$(SolutionDir)|Geçerli çözüme (sürücü + yolu) dizini.|  
|Çözüm dosyası adı|$(SolutionFileName)|Dosya adı, geçerli çözüme (sürücü + yolu + dosya adı).|  

## <a name="see-also"></a>Ayrıca bkz.  
 [C/C++ derleme araçları](/cpp/build/reference/c-cpp-build-tools)
