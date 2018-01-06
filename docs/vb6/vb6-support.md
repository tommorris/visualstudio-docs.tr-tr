---
title: "Visual Basic 6.0 deyimi desteği | Microsoft Docs"
ms.date: 08/28/2017
ms.technology: devlang-visual-basic
ms.topic: article
dev_langs: VB
helpviewer_keywords:
- VB6 support
- Visual Basic 6.0 support
ms.assetid: ffc5ba4d-44d7-4ef7-a3f6-38a8738bf127
author: paulyuk
ms.author: paulyuk
ms.workload: paulyuk
ms.openlocfilehash: a8977aad735a115089685ed0032b3d358d8b89c8
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="support-statement-for-visual-basic-60-on-windows"></a>Visual Basic 6.0 Windows deyimi desteği


## <a name="executive-summary"></a>Özet

Aşağıdaki desteklenen Windows işletim sistemlerinde Visual Basic 6.0 uygulamalar için "Sadece çalışır" uyumluluk için Visual Basic team adamıştır: 

- Windows 10
- Windows 8.1
- Windows 7
- Windows Server 2016
- Windows Server 2012 R2'de dahil olmak üzere
- Windows Server 2008 R2'de dahil olmak üzere

Visual Basic takımınızın hedefinin, Visual Basic 6.0 uygulamalarını desteklenen Windows sürümleri üzerinde çalışmasını devam edemiyor. Bu belgedeki olarak ayrıntılı, çekirdek Visual Basic 6.0 çalışma zamanı desteklenen Windows sürümlerine tam ömrü boyunca tarafından beş yıl genişletilmiş destek (http://support.microsoft.com/gp/lifepolicy) ve ardından temel desteğinin beş yıl olduğu desteklenmez. Destek Çubuğu ciddi gerileme ve mevcut uygulamalar için kritik güvenlik sorunları için sınırlı olacaktır.

## <a name="technical-summary"></a>Teknik özeti

Visual Basic 6.0 Bu anahtar sonuçlara oluşur:
- Visual Basic 6.0 IDE (tümleşik geliştirme ortamı).
- Visual Basic 6.0 çalışma zamanı: temel kitaplıkları ve VB 6.0 uygulamaları çalıştırmak için kullanılan yürütme altyapısı.
- Visual Basic 6.0 Çalışma Zamanı Genişletilmiş dosyaları: Seçili ActiveX denetim OCX dosyaları, kitaplıklar ve çevrimiçi bir sürüm olarak IDE ortam ile sevkiyat araçları.

## <a name="the-visual-basic-60-ide"></a>Visual Basic 6.0 IDE

Visual Basic 6.0 IDE 8 Nisan 2008'den itibaren artık desteklenmiyor. Ayrıca, Visual Basic 6.0 IDE üzerinde Windows Vista, Windows 7, Windows Server 2008, Windows 8 ve Windows 8.1 anlamak ve (gerekirse) azaltmak için hem Windows hem de Visual Basic takımlar sınanmıştır (bkz. Windows 32-bit sürümlerinde uyumluluk sorunları [64-Bit Windows](#62-bit-windows) 64 bit sistemler hakkında daha fazla bilgi için bölüm aşağıda). Bu duyuru destek ilkesi için IDE değiştirmez.

## <a name="the-visual-basic-60-runtime"></a>Visual Basic 6.0 çalışma zamanı

Visual Basic 6.0 çalışma zamanı, başlangıçta yeniden dağıtımı için Visual Basic 6.0 listede derlenmiş ikili dosyaları olarak tanımlanır. Bu dosyalar, özgün Visual Basic 6.0 lisans dağıtılabilir olarak işaretlendi. Bu dosyalar örnekler Visual Basic 6.0 çalışma zamanı kitaplığı (`msvbvm60.dll`), denetimleri (yani, `msflxgrd.ocx`) ile birlikte çalışma zamanı dosyaları diğer önemli işlevsel alanlara (yani MDAC) için destek.

Çalışma zamanı üç gruplar halinde ayrılır:

- Çalışma zamanı dosyalarını--desteklenen işletim sisteminde aktarma

   Uygulama senaryoları çoğunluğu içinde kullanılan anahtarı Visual Basic 6.0 çalışma zamanı dosyaları içinde sevkiyat ve desteklenen Windows sürümlerine ömrü için desteklenir. Bu ömrü temel desteğinin beş yıl ve belirli bir Windows sürümü gelir zamandan itibaren genişletilmiş desteğinin beş yıl ' dir. Bu dosyalar üzerinde desteklenen Windows sürümlerini çalıştıran Visual Basic 6.0 uygulamalarının bizim test bir parçası olarak uyumluluk için test edilmiştir. 

   > [!NOTE]
   > Tüm desteklenen Windows sürümlerine neredeyse aynı dosyaların listesini içeren ve bu dosyaları içeren uygulamalar için redist gereksinimleri neredeyse aynı olmalıdır. Temel farklardan biri olan `TriEdit.dll` Windows Vista ve sonraki sürümlerinde kaldırılmıştır.

- Çalışma zamanı dosyalarını – desteklenen-genişletilmiş ile uygulamanızı dağıtmak için dosyaları

   Bu Genişletilmiş liste anahtar denetimleri, kitaplıklar ve IDE medyadan yükleme veya Microsoft.com Geliştirici makineye yüklenir araçları oluşur. Genellikle, VB6 IDE bu denetimleri Geliştirici makineye varsayılan olarak yüklenir. Geliştirici hala uygulamayla bu dosyaları yeniden dağıtmanız gerekir. Dosyaları'nın desteklenen sürümünü, çevrimiçi Microsoft Download Center (http://go.microsoft.com/fwlink/?LinkID=142927) kullanılabilir.

- Desteklenmeyen çalışma zamanı dosyaları

   Bazı dosyalar ya da temel dışında düşmüş desteklemek veya hiç çalışma zamanı redist bir parçası olarak dahil edilen (örn., bunlar eklenmiş olan `\Tools` eski VB4/VB5 uygulamaları desteklemek için IDE ortam klasöründe veya üçüncü taraf denetimleri oldukları). Bu dosyalar Windows desteklenmez; Bunun yerine herhangi bir destek sözleşmesi sevk edilen medya uygulandığı tabi oldukları. Bu, hiçbir garanti destek ve Bakım etrafında anlamına gelir. Bazı durumlarda, bu kitaplıkları'nın sonraki sürümleri desteklenir. Geriye dönük uyumluluk veya geçiş için desteklenen sürümleri hakkında ayrıntılar aşağıda verilmiştir.

Her destek grubu içinde bulunan dosyalar üzerinde belirli Ayrıntılar için bkz: [çalışma zamanı tanımı](#runtime-definition) bölümüne bakın.

## <a name="the-visual-basic-60-support-lifetime"></a>Visual Basic 6.0 destek ömrü

Destek İlkesi destekleme ve/veya Visual Basic 6.0 çalışma zamanı ikili dosyalarını desteklenen Windows sürümlerine sevkiyat Visual Basic 6.0 IDE veya Visual Studio 6.0 IDE için bir bütün olarak değiştirmez. Genişletilmiş Destek 8 Nisan 2008 dışında bu ürünlerden taşındı.

Microsoft ürün desteği yaşam döngüsü hakkında ayrıntılar http://support.microsoft.com/gp/lifepolicy bulunabilir. Bu destek yaşam döngüsü kapsamında, Microsoft Visual Basic 6.0 çalışma zamanı bu işletim sistemleri için destek ömrü desteklenen Windows sürümlerine desteklemeye devam eder. Bu, örneğin, Visual Basic 6.0 çalışma zamanı Windows Server 2003'te Haziran 2008 için temel destek ve genişletilmiş destek Haziran 2013 kadar desteklenecek anlamına gelir.
Destek yaşam döngüsü veya ek destek seçenekleri hakkında bilgi almak için daha fazla ayrıntı için lütfen http://www.microsoft.com/support adresindeki destek sayfamızı ziyaret edin.

## <a name="64-bit-windows"></a>64 bit Windows

Visual Basic 6.0 çalışma zamanı dosyalarını 32-bit. Bu dosyalar, 64-bit Windows işletim aşağıdaki tabloda başvurulan sistemleri birlikte. 32-bit VB6 uygulamaları ve bileşenleri yalnızca WOW öykünme ortamında desteklenir. 32-bit bileşenleri de 32 bit uygulama işlemlerini barındırılması gerekir.

Visual Basic 6.0 IDE hiçbir zaman bir yerel 64 bit sürümünde sunulan ve 32-bit IDE 64-bit Windows sürümlerinde desteklenir. Windows'un 64-bit veya 32 bit dışındaki herhangi bir yerel mimarideki VB6 geliştirme değil ve desteklenmeyecek.

## <a name="windows-7"></a>Windows 7

Bu destek ifadesi ilk yayımlandıktan sonra Windows 7 işletim sistemi yayımladı. Bu belge, Windows 7 VB6 Microsoft'un desteği açıklamak için güncelleştirilmiştir.

VB6 çalışma zamanı sevk edecek ve Windows 7'de işletim sistemi ömrü boyunca desteklenecektir. Visual Basic 6.0 çalışma zamanı dosyaları yalnızca 32-bit devam ve tüm bileşenlerini 32 bit uygulama işlemlerini barındırılması gerekir.

## <a name="windows-81"></a>Windows 8.1

Bu destek ifadesi ilk yayımlandıktan sonra Windows 8.1 işletim sistemi yayımladı. Bu belge, Windows 8.1 üzerindeki VB6 Microsoft'un desteği açıklamak için güncelleştirilmiştir.

VB6 çalışma zamanı sevk edecek ve Windows 8.1 işletim sistemi ömrü boyunca desteklenecektir. Visual Basic 6.0 çalışma zamanı dosyaları yalnızca 32-bit devam ve tüm bileşenlerini 32 bit uygulama işlemlerini barındırılması gerekir. Geliştiriciler destek öyküsü Windows 8.1 için Windows 7 için olduğu gibi aynı olarak düşünebilirsiniz.

## <a name="windows-10"></a>Windows 10

Bu destek ifadesi ilk yayımlandıktan sonra Windows 10 işletim sistemi yayımladı. Bu belge, VB6 Windows 10 için Microsoft destek açıklamak için güncelleştirilmiştir.

VB6 çalışma zamanı sevk edecek ve Windows 10 işletim sistemi ömrü boyunca desteklenecektir. Visual Basic 6.0 çalışma zamanı dosyaları yalnızca 32-bit devam ve tüm bileşenlerini 32 bit uygulama işlemlerini barındırılması gerekir. Geliştiriciler destek öyküsü Windows 10 için Windows 8.1 için olduğu gibi aynı olarak düşünebilirsiniz.

## <a name="windows-server-2008"></a>Windows Server 2008

Bu destek ifadesi ilk yayımlandıktan sonra Windows Server 2008 işletim sistemi yayımladı. Bu belge, Windows Server 2008 üzerinde VB6 Microsoft'un desteği açıklamak için güncelleştirilmiştir.

VB6 çalışma zamanı sevk edecek ve Windows Server 2008'de işletim sistemi ömrü boyunca desteklenecektir. Visual Basic 6.0 çalışma zamanı dosyaları yalnızca 32-bit devam ve tüm bileşenlerini 32 bit uygulama işlemlerini barındırılması gerekir.

## <a name="windows-server-2008-r2"></a>Windows Server 2008 R2

Bu destek ifadesi ilk yayımlandıktan sonra Windows Server 2008 R2 işletim sistemi yayımladı. Bu belge, Windows Server 2008 R2 üzerinde VB6 Microsoft'un desteği açıklamak için güncelleştirilmiştir.

VB6 çalışma zamanı sevk edecek ve Windows Server 2008 R2'de işletim sistemi ömrü boyunca desteklenecektir. Visual Basic 6.0 çalışma zamanı dosyaları yalnızca 32-bit devam ve tüm bileşenlerini 32 bit uygulama işlemlerini barındırılması gerekir. Geliştiriciler destek öyküsü Windows Server 2008 R2 için Windows Server 2008 için olduğu gibi aynı olarak düşünebilirsiniz.

## <a name="windows-server-2012"></a>Windows Server 2012

Bu destek ifadesi ilk yayımlandıktan sonra Windows Server 2012 işletim sistemi yayımladı. Bu belge, Windows Server 2012 VB6 Microsoft'un desteği açıklamak için güncelleştirilmiştir.

VB6 çalışma zamanı sevk edecek ve Windows Server 2012'de işletim sistemi ömrü boyunca desteklenecektir. Visual Basic 6.0 çalışma zamanı dosyaları yalnızca 32-bit devam ve tüm bileşenlerini 32 bit uygulama işlemlerini barındırılması gerekir. Geliştiriciler destek öyküsü Windows Server 2012 için Windows Server 2008 R2 için olduğu gibi aynı olarak düşünebilirsiniz.

## <a name="windows-server-2012-r2"></a>Windows Server 2012 R2

Bu destek ifadesi ilk yayımlandıktan sonra Windows Server 2012 R2 işletim sistemi yayımladı. Bu belge, Windows Server 2012 R2 üzerinde VB6 Microsoft'un desteği açıklamak için güncelleştirilmiştir.

VB6 çalışma zamanı sevk edecek ve Windows Server 2012 R2'de işletim sistemi ömrü boyunca desteklenecektir. Visual Basic 6.0 çalışma zamanı dosyaları yalnızca 32-bit devam ve tüm bileşenlerini 32 bit uygulama işlemlerini barındırılması gerekir. Geliştiriciler destek öyküsü Windows Server 2012 R2 için Windows Server 2012 için olduğu gibi aynı olarak düşünebilirsiniz.

## <a name="windows-server-2016"></a>Windows Server 2016

Bu destek ifadesi ilk yayımlandıktan sonra Windows Server 2016 işletim sistemi yayımladı. Bu belge, Windows Server 2016 VB6 Microsoft'un desteği açıklamak için güncelleştirilmiştir.

VB6 çalışma zamanı sevk edecek ve Windows Server 2016'işletim sistemi ömrü boyunca desteklenecektir. Visual Basic 6.0 çalışma zamanı dosyaları yalnızca 32-bit devam ve tüm bileşenlerini 32 bit uygulama işlemlerini barındırılması gerekir. Geliştiriciler destek öyküsü Windows Server 2016 için Windows Server 2012 R2 için olduğu gibi aynı olarak düşünebilirsiniz.

## <a name="supported-windows-operating-system-versions"></a>Desteklenen Windows işletim sistemi sürümleri

Bu bölümde, belirli bir düzeyde VB6 desteği sunar işletim sistemleri ile ilgili ek bilgiler sağlar. 

|Windows işletim sistemi|VB6 Desteklenen çalışma zamanı</br>Windows'da sevkiyat dosyaları desteğine sahip mi?|VB6 Desteklenen Rutime</br>Genişletilmiş dosyaları</br>uygulamanız ile dağıtmak için desteğe sahip mi?| VB6 IDE desteği vardır?|
|---|---|---|---|
|Windows 10, tüm 32 bit sürümleri|Evet *|Evet *|Hayır|
|Windows 10, tüm 64 bit sürümleri (yalnızca WOW)|Evet * </br> içinde WOW yalnızca çalışan 32-bit uygulamalar|Evet* </br> içinde WOW yalnızca çalışan 32-bit uygulamalar|Hayır|
|Windows 8.1, tüm 32 bit sürümleri|Evet *|Evet *|Hayır|
| Windows 8.1, tüm 64 bit sürümleri (yalnızca WOW)|Evet * </br> içinde WOW yalnızca çalışan 32-bit uygulamalar|Evet* </br> içinde WOW yalnızca çalışan 32-bit uygulamalar|Hayır|
|Windows 7, tüm 32 bit sürümleri|Evet *|Evet *|Hayır|
|Windows 7, tüm 64 bit sürümleri (yalnızca WOW)|Evet * </br> içinde WOW yalnızca çalışan 32-bit uygulamalar|Evet * </br> içinde WOW yalnızca çalışan 32-bit uygulamalar|Hayır|
|Windows Server 2016, tüm 64 bit sürümleri (yalnızca WOW)|Evet* </br> içinde WOW yalnızca çalışan 32-bit uygulamalar|Evet* </br> içinde WOW yalnızca çalışan 32-bit uygulamalar|Hayır|
|Windows Server 2012 R2, tüm 64 bit sürümleri (yalnızca WOW)<br>Windows Server 2012, tüm 64 bit sürümleri (yalnızca WOW)|Evet* </br> içinde WOW yalnızca çalışan 32-bit uygulamalar|Evet* </br> içinde WOW yalnızca çalışan 32-bit uygulamalar|Hayır|
|Windows Server 2008 R2, tüm x64 sürümleri (yalnızca WOW)</br>Windows Server 2008 ' in tüm x64 sürümleri (yalnızca WOW)|Evet * </br> içinde WOW yalnızca çalışan 32-bit uygulamalar|Evet * </br> içinde WOW yalnızca çalışan 32-bit uygulamalar|Hayır|
|Windows Server 2008 ' in tüm 32 bit sürümleri|Evet *|Evet *|Hayır|


> [!NOTE]
> &#42;  Windows destek yaşam döngüsü tarafından sınırlı bir VB6 çalışma zamanı desteği.  Örneğin, hedef işletim sistemi genişletilmiş destekte yer ise, VB6 genişletilmiş destek destek daha üst bir düzeyde olamaz.  [Windows destek yaşam döngüsü olgu sayfası](https://support.microsoft.com/en-us/help/13853/windows-lifecycle-fact-sheet) geçerli ve önceki Windows sürümleri hakkında ek yaşam döngüsü bilgi içerir.

## <a name="visual-basic-60-runtime-usage-inside-vba-and-office"></a>Visual Basic 6.0 çalışma zamanı kullanım VBA ve Office içinde

Visual Basic for uygulamaları veya VBA, uygulama Otomasyonu ve Microsoft Office uygulamaları içinde yaygın diğer uygulamaları içinde makroları için yaygın olarak kullanılan ayrı bir teknolojidir. VBA Office bir parçası olarak gönderilen ve bu nedenle VBA desteği Office destek ilkesi tarafından yönetilir. Ancak, VBA arayın veya Visual Basic 6.0 çalışma zamanı ikili dosyaları ve denetimleri barındırmak için kullanıldığı durumlar vardır. Bu durumlarda, Visual Basic 6.0 çalışma zamanı dosyalarını işletim sisteminde desteklenir ve genişletilmiş dosya listesini da içinde desteklenen VBA ortamını kullanıldığında desteklenir.

VBA desteklenecek VB6 çalışma zamanı senaryoları için aşağıdakilerin tümü doğru olmalıdır:

- VB çalışma zamanı için ana bilgisayar işletim sistemi sürümü hala desteklenmektedir.
- VBA için Office ana sürümü hala desteklenmektedir.
- Söz konusu çalışma zamanı dosyalarını hala desteklenmektedir.

## <a name="visual-basic-script-vbscript"></a>Visual Basic betiği (VBScript)

Visual Basic 6.0 ve bu destek ifadesi ilgisiz VBScript'tir. Ancak, VBScript şu anda Windows 7, Windows 8.1, Windows 10, Windows Server 2008 R2, Windows Server 2012 R2 ve Windows Server 2016 dahil olmak üzere de dahil olmak üzere bir parçası olarak mevcut ve işletim sistemi destek yaşam döngüsü tarafından yönetilir.

## <a name="third-party-components"></a>Üçüncü taraf bileşenleri

Microsoft OCX/ActiveX denetimleri gibi üçüncü taraf bileşenleri için destek sağlayabilirsiniz alamıyor. Müşteriler bu bileşenler için destek hakkında ayrıntılar için özgün denetim satıcısına başvurmanız önerilir.

## <a name="reporting-issues-with-vb-60-applications-running-on-windows"></a>Windows üzerinde çalışan VB 6.0 uygulamalarıyla raporlama sorunları

Geliştiriciler Visual Basic 6.0 listelenen Windows işletim sistemlerinden biri ile kullanmak planlama, bu işletim sistemini yüklemek ve özgün uygulama kabul testi kullanarak uygulama uyumluluğu sınaması başlar.

Listelenen Windows işletim sistemlerinden birini çalıştıran Visual Basic 6.0 uygulamanız ile ilgili bir sorun bulursanız, Lütfen sorunu bildirmek için normal destek kanallarınıza izleyin.

## <a name="supported-and-shipping-in-windows"></a>Desteklenen ve içinde sevkiyat Windows

| | | | |
|---|---|---|---|
|ATL.|         msadcor.dll|     msorcl32.dll|   başlatılan OLE2.dll|
|Asycfilt.dll|    Msadcs.dll|      Msvbvm60.dll|   Ole32.dll|
|comcat.dll|      msadds.dll|      Msvcirt.dll|    Oleaut32.dll|
|compobj.dll|     msaddsr.dll|     Msvcrt.dll|     Oleaut32.dll|
|dbnmpntw.dll|    msader15.dll|    msvcrt40.dll|   Oledb32.dll|
|Dcomcnfg.exe'yi|    Msado15.dll|     Mtxdm.dll|      oledb32r.dll|
|Dllhost.exe|     msador15.dll|    Mtxoci.dll|     oledlg.dll|
|ds16gt.dll|      msadrh15.dll|    odbc16gt.dll|   Olepro32.dll|
|ds32gt.dll|      mscpxl32.dll|    Odbc32.dll|     olethk32.dll|
|expsrv.dll|      msdadc.dll|      odbc32gt.dll|   Regsvr32.exe|
|hh.exe|          msdaenum.dll|    odbcad32.exe|   rpcns4.dll|
|Hhctrl.ocx|      msdaer.dll|      Odbccp32.cpl|   Rpcrt4.dll|
|Imagehlp.dll|    MSDAORA.dll|     Odbccp32.dll|   Scrrun.dll|
|iprop.dll|       msdaosp.dll|     Odbccr32.dll|   Secur32.dll|
|Itircl.dll|      Msdaprst.dll|    odbccu32.dll|   simpdata.tlb|
|Itss.dll|        msdaps.dll|      odbcint.dll|    Sqloledb.dll|
|mfc40.dll|       msdasc.dll|      odbcji32.dll|   Sqlsrv32.dll|
|MFC42.dll|       MSDASQL.dll|     ODBCJT32.dll|   Stdole2.tlb|
|mfc42enu.dll|    msdasqlr.dll|    Odbctrac.dll|   stdole32.tlb|
|msadce.dll|      msdatsrc.tlb|    oddbse32.dll|   Storage.dll|
|msadcer.dll|     msdatt.dll|      odexl32.dll|    VBAJET32.dll|
|msadcf.dll|      MSDFMAP.dll|     odfox32.dll|    Vfpodbc.dll|
|msadcfr.dll|     MSDFMAP.ini|     odpdx32.dll|                |
|Msadco.dll|      msjtes40.dll|    Odtext32.dll|               |

## <a name="supported-runtime-files-to-distribute-with-your-application"></a>Uygulamanız ile dağıtmak için desteklenen çalışma zamanı dosyaları

| | | | |
|---|---|---|---|
|comct232.ocx |msbind.dll   |msdbrptr.dll  |MSstdfmt.dll| 
|comct332.ocx |mscdrun.dll  |msflxgrd.ocx  |Msstkprp.dll'in| 
|Comctl32.ocx |Mschrt20.ocx |mshflxgd.ocx  |mswcrun.dll|  
|comdlg32.ocx |mscomct2.ocx |mshtmpgr.dll  |Mswinsck.ocx| 
|dbadapt.dll  |Mscomctl.ocx |msinet.ocx    |picclp32.ocx| 
|dbgrid32.ocx |mscomm32.ocx |Msmapi32.ocx  |richtx32.ocx| 
|dblist32.ocx |msdatgrd.ocx |Msmask32.ocx  |sysinfo.ocx|  
|mci32.ocx    |msdatlst.ocx |msrdc20.ocx   |tabctl32.ocx| 
|msadodc.ocx  |msdatrep.ocx |Msrdo20.dll

## <a name="unsupported-but-supported-and-compatible-updates-or-upgrades-are-available"></a>Desteklenmeyen, ancak desteklenen ve uyumlu güncelleştirmeleri veya yükseltmeleri kullanılabilir

| | | | |
|---|---|---|---|
|dao350.dll|   msexch35.dll| msjter35.dll| msrepl35.dll|
|Mdac_typ.exe'yi| msexcl35.dll| msjtor35.dll| Mstext35.dll|
|MSChart.ocx|  MSJET35.dll|  msltus35.dll| msxbse35.dll|
|msdaerr.dll|  msjint35.dll| Mspdox35.dll| odbctl32.dll|
|msdatl2.dll|  msjt4jlt.dll| msrd2x35.dll| oledb32x.dll|

## <a name="unsupported-runtime-files"></a>Desteklenmeyen çalışma zamanı dosyaları

| | | | |
|---|---|---|---|
|anibtn32.ocx| spin32.ocx|   rpcltscm.dll|  RDOCURS.dll|
|graph32.ocx|  gauge32.ocx|  rpcmqcl.dll|   vbar332.dll|
|keysta32.ocx| gswdll32.dll| rpcmqsvr.dll|  visdata.exe|
|autmgr32.exe| ciscnfg.exe|  Rpcss.exe|     vsdbflex.srg|
|autprx32.dll| Olecnv32.dll| dbmsshrn.dll|  threed32.ocx|
|racmgr32.exe| rpcltc1.dll|  Dbmssocn.dll|  MSWLess.ocx|
|racreg32.dll| rpcltc5.dll|  windbver.exe|  Tlbinf32.dll|
|grid32.ocx|   rpcltccm.dll| msderun.dll|   triedit.dll|
|msoutl32.ocx| rpclts5.dll|  odkob32.dll|

## <a name="localization-support-binaries"></a>Yerelleştirme Destek İkili dosyalar

Aşağıdaki ikili dosyalar, Windows işletim sisteminin yerelleştirilmiş sürümlerini çalıştıran Visual Basic 6.0 uygulamalarını desteklemek için gereklidir. Bunlar desteklenir, ancak Windows gönderilmeyen. Bu dosyalar uygulama kurulumunuzu edilmeye gereklidir.

### <a name="supported-runtime-files-to-distribute-with-your-application"></a>Uygulamanız ile dağıtmak için desteklenen çalışma zamanı dosyaları

|JPN|KOR|CHT|CHS|
|---|---|---|---|
|mfc42jpn.dll|  mfc42kor.dll|  mfc42cht.dll|  mfc42chs.dll|
|scrrnjp.dll|   scrrnko.dll|   scrrncht.dll|  scrrnchs.dll|
|vb6jp.dll|     vb6ko.dll|     vb6cht.dll|    vb6chs.dll|
|cmct2jp.dll|   cmct2ko.dll|   cmct2cht.dll|  cmct2chs.dll|
|cmct3jp.dll|   cmct3ko.dll|   cmct3cht.dll|  mscc2chs.dll|
|mscc2jp.dll|   mscc2ko.dll|   mscc2cht.dll|  cmct3chs.dll|
|cmctljp.dll|   cmctlko.dll|   cmctlcht.dll|  cmctlchs.dll|
|cmdlgjp.dll|   cmdlgko.dll|   mscmccht.dll|  mscmcchs.dll|
|mscmcjp.dll|   mscmcko.dll|   cmdlgcht.dll|  cmdlgchs.dll|
|dbgrdjp.dll|   dbgrdko.dll|   dbgrdcht.dll|  dbgrdchs.dll|
|dblstjp.dll|   dblstko.dll|   dblstcht.dll|  dblstchs.dll|
|mcijp.dll|     mciko.dll|     mcicht.dll|    mcichs.dll|
|msadnjp.dll|   msadnko.dll|   msadncht.dll|  msadnchs.dll|
|adodcjp.dll|   adodcko.dll|   adodccht.dll|  adodcchs.dll|
|mschtjp.dll|   mschtko.dll|   mschtcht.dll|  mschtchs.dll|
|msch2jp.dll|   msch2ko.dll|   msch2cht.dll|  msch2chs.dll|
|mscomjp.dll|   mscomko.dll|   mscomcht.dll|  mscomchs.dll|
|datgdjp.dll|   datgdko.dll|   datgdcht.dll|  datgdchs.dll|
|datlsjp.dll|   datlsko.dll|   datlscht.dll|  datlschs.dll|
|datrpjp.dll|   datrpko.dll|   datrpcht.dll|  datrpchs.dll|
|dbrprjp.dll|   dbrprko.dll|   dbrprcht.dll|  dbrprchs.dll|
|flxgdjp.dll|   flxgdko.dll|   flxgdcht.dll|  flxgdchs.dll|
|mshfgjpn.dll|  mshfgkor.dll|  mshfgcht.dll|  mshfgchs.dll|
|htmprjp.dll|   htmprko.dll|   htmprcht.dll|  htmprchs.dll|
|inetjp.dll|    inetko.dll|    inetcht.dll|   inetchs.dll|
|msmpijp.dll|   msmpiko.dll|   msmpicht.dll|  msmpichs.dll|
|msmskjp.dll|   msmskko.dll|   msmskcht.dll|  msmskchs.dll|
|rdc20jp.dll|   rdc20ko.dll|   rdc20cht.dll|  rdc20chs.dll|
|rdo20jp.dll|   rdo20ko.dll|   rdo20cht.dll|  rdo20chs.dll|
|stdftjp.dll|   stdftko.dll|   stdftcht.dll|  stdftchs.dll|
|mswcrjp.dll|   mswcrko.dll|   mswcrcht.dll|  mswcrchs.dll|
|winskjp.dll|   winskko.dll|   winskcht.dll|  winskchs.dll|
|pcclpjp.dll|   pcclpko.dll|   pcclpcht.dll|  pcclpchs.dll|
|rchtxjp.dll|   rchtxko.dll|   rchtxcht.dll|  rchtxchs.dll|
|sysinjp.dll|   sysinko.dll|   sysincht.dll|  sysinchs.dll|
|tabctjp.dll|   tabctko.dll|   tabctcht.dll|  tabctchs.dll|

|ITA|FRA|ESP|DEU|
|---|---|---|---|
|mfc42ita.dll|  mfc42fra.dll|  mfc42esp.dll|  mfc42deu.dll|
|scrrnit.dll|   scrrnfr.dll|   scrrnes.dll|   scrrnde.dll|
|vb6it.dll|     vb6fr.dll|     vb6es.dll|     vb6de.dll|
|cmct2it.dll|   cmct2fr.dll|   cmct2es.dll|   cmct2de.dll|
|mscc2it.dll|   mscc2fr.dll|   mscc2es.dll|   mscc2de.dll|
|cmct3it.dll|   cmct3fr.dll|   cmct3es.dll|   cmct3de.dll|
|cmctlit.dll|   cmctlfr.dll|   cmctles.dll|   cmctlde.dll|
|mscmcit.dll|   mscmcfr.dll|   mscmces.dll|   mscmcde.dll|
|cmdlgit.dll|   cmdlgfr.dll|   cmdlges.dll|   cmdlgde.dll|
|dbgrdit.dll|   dbgrdfr.dll|   dbgrdes.dll|   dbgrdde.dll|
|dblstit.dll|   dblstfr.dll|   dblstes.dll|   dblstde.dll|
|mciit.dll|     mcifr.dll|     mcies.dll|     mcide.dll|
|msadnit.dll|   msadnfr.dll|   msadnes.dll|   msadnde.dll|
|adodcit.dll|   adodcfr.dll|   adodces.dll|   adodcde.dll|
|mschtit.dll|   mschtfr.dll|   mschtes.dll|   mschtde.dll|
|msch2it.dll|   msch2fr.dll|   msch2es.dll|   msch2de.dll|
|mscomit.dll|   mscomfr.dll|   mscomes.dll|   mscomde.dll|
|atgdit.dll|    datgdfr.dll|   datgdes.dll|   datgdde.dll|
|datlsit.dll|   datlsfr.dll|   datlses.dll|   datlsde.dll|
|datrpit.dll|   datrpfr.dll|   datrpes.dll|   datrpde.dll|
|dbrprit.dll|   dbrprfr.dll|   dbrpres.dll|   dbrprde.dll|
|flxgdit.dll|   flxgdfr.dll|   flxgdes.dll|   flxgdde.dll|
|mshfgit.dll|   mshfgfr.dll|   mshfges.dll|   mshfgde.dll|
|htmprit.dll|   htmprfr.dll|   htmpres.dll|   htmprde.dll|
|inetit.dll|    inetfr.dll|    inetes.dll|    inetde.dll|
|msmpiit.dll|   msmpifr.dll|   msmpies.dll|   msmpide.dll|
|msmskit.dll|   msmskfr.dll|   msmskes.dll|   msmskde.dll|
|rdc20it.dll|   rdc20fr.dll|   rdc20es.dll|   rdc20de.dll|
|rdo20it.dll|   rdo20fr.dll|   rdo20es.dll|   rdo20de.dll|
|stdftit.dll|   stdftfr.dll|   stdftes.dll|   stdftde.dll|
|mswcrit.dll|   mswcrfr.dll|   mswcres.dll|   mswcrde.dll|
|winskit.dll|   winskfr.dll|   winskes.dll|   winskde.dll|
|pcclpit.dll|   pcclpfr.dll|   pcclpes.dll|   pcclpde.dll|
|rchtxit.dll|   rchtxfr.dll|   rchtxes.dll|   rchtxde.dll|
|sysinit.dll|   sysinfr.dll|   sysines.dll|   sysinde.dll|
|tabctit.dll|   tabctfr.dll|   tabctes.dll|   tabctde.dll|

