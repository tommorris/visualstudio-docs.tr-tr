---
title: "Proje çıktı için yapılandırma | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- project configurations, output
ms.assetid: a4517f73-45af-4745-9d7f-9fddf887b636
caps.latest.revision: 
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload:
- vssdk
ms.openlocfilehash: 4f3927ac9aa9e85be026d2b9a2af1c0c4d956c9f
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="project-configuration-for-output"></a>Çıktı için proje yapılandırması
Her yapılandırma çıktı öğeleri yürütülebilir dosya veya kaynak dosyaları gibi üretmek yapı işlemler kümesini destekler. Bu çıktı öğeler kullanıcıya özeldir ve yürütülebilir dosyalar (.exe, .dll, .lib) ve kaynak dosyaları (.idl, .h dosyaları) gibi bir çıkış ilgili türleri bağlantı grupları yerleştirilebilir.  
  
 Çıktı öğeleri kullanılabilir hale getirebilir aracılığıyla <xref:Microsoft.VisualStudio.Shell.Interop.IVsOutput2> yöntemleri ve ile numaralandırılmış <xref:Microsoft.VisualStudio.Shell.Interop.IVsEnumOutputs> yöntemleri. Çıktı öğeleri gruplandırmak için istediğinizde, projenizin de uygulamalıdır <xref:Microsoft.VisualStudio.Shell.Interop.IVsOutputGroup> arabirimi.  
  
 Yapı geliştirilen uygulayarak `IVsOutputGroup` grup çıkışları kullanım göre projelerine sağlar. Örneğin, DLL, program veritabanı (PDB) gruplandırılmış olabilir.  
  
> [!NOTE]
>  PDB dosyası hata ayıklama bilgileri içerir ve 'Hata ayıklama bilgisi Oluştur' seçeneğini .dll veya .exe oluştururken belirtildiğinde oluşturulur. .Pdb dosyasını genellikle yalnızca hata ayıklama proje yapılandırma oluşturulur.  
  
 Bir gruptaki çıkışları sayısı yapılandırma yapılandırması değişebilir olsa bile Proje grupları destekliyorsa, her yapılandırma için aynı sayıda döndürmesi gerekir. Örneğin, projenin Matt DLL mattd.dll ve mattd.pdb hata ayıklama yapılandırmasını da dahil, ancak yalnızca matt.dll perakende yapılandırmasında dahildir.  
  
 Grupları kurallı adı, görünen ad ve grup bilgileri gibi aynı kimliği bilgilerini yapılandırma yapılandırması bir projede de. Bu tutarlılık, dağıtım ve yapılandırmaları değişse bile çalışmaya devam etmek için paketleme sağlar.  
  
 Grupları, anlamlı işaret edecek şekilde paketleme kısayolları izin veren bir anahtar çıktı olarak da sağlayabilirsiniz. Bir grup boyutu hakkında hiçbir varsayımlar yapılması gereken şekilde herhangi bir grubu belirli bir yapılandırmada boş olabilir. Her grupta herhangi bir yapılandırma boyutu (çıkışları sayısı) aynı yapılandırmayı başka bir grupta boyutundan farklı olabilir. Ayrıca başka bir yapılandırma aynı grupta boyutundan farklı olabilir.  
  
 ![Çıktı grupları grafiği](../../extensibility/internals/media/vsoutputgroups.gif "vsOutputGroups")  
Çıktı grupları  
  
 Birincil kullanımını <xref:Microsoft.VisualStudio.Shell.Interop.IVsProjectCfg> arabirimidir oluşturun, dağıtın ve yönetim nesneleri hata ayıklama ve projeleri grup çıkışları serbestçe izin vermek için erişim sağlamak için. Bu arabirim kullanımı hakkında daha fazla bilgi için bkz: [proje yapılandırma nesnesi](../../extensibility/internals/project-configuration-object.md).  
  
 Önceki diyagramda grup yerleşik yapılandırmaları (bD.exe veya b.exe) bu nedenle çıktı bir anahtara sahip kullanıcı yerleşik bir kısayol oluşturun ve bilmeniz kısayol dağıtılan yapılandırma bağımsız olarak çalışır. Kullanıcı bir kısayol oluşturamaz şekilde grubu kaynağı çıktı, bir anahtar yok. Hata ayıklama grup yerleşik anahtar çıkış sahiptir, ancak perakende yerleşik grup yok ise, yanlış bir uygulama olabilir. Herhangi bir yapılandırma yok çıkışları içeren bir grup varsa, daha sonra izleyen ve sonuç olarak, anahtar dosyası sonra çıkışları içeren diğer yapılandırmaları grubu ile anahtar dosyaları sahip olamaz. Yükleyici düzenleyicileri kurallı adları ve görünen adları gruplarının yanı sıra, bir anahtar dosyası varlığını değiştirmeyin yapılandırmalarında tabanlı varsayalım.  
  
 Bir proje varsa unutmayın bir `IVsOutputGroup` paketini veya dağıtmak istediğinizi değil, onu bu çıkışı bir gruba yerleştirmek değil yeterlidir. Çıktı hala normalde uygulayarak numaralandırılabilir <xref:Microsoft.VisualStudio.Shell.Interop.IVsProjectCfg.EnumOutputs%2A> tüm gruplandırma bakılmaksızın bir yapılandırmasının çıkışları döndürüyor yöntemi.  
  
 Daha fazla bilgi için bkz: `IVsOutputGroup` özel Proje örnekteki [projelerinin MPF](http://mpfproj12.codeplex.com).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Yapılandırma seçenekleri yönetme](../../extensibility/internals/managing-configuration-options.md)   
 [Proje yapılandırması oluşturmak için](../../extensibility/internals/project-configuration-for-building.md)   
 [Proje yapılandırma nesnesi](../../extensibility/internals/project-configuration-object.md)   
 [Çözüm Yapılandırması](../../extensibility/internals/solution-configuration.md)