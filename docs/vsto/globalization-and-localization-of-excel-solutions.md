---
title: Genelleştirme ve yerelleştirme Excel çözümleri
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- globalization [Office development in Visual Studio], configuring
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: ecd88a238c783224dc9d1ea982fe1ed3970fcfc1
ms.sourcegitcommit: 1466ac0f49ebf7448ea4507ae3f79acb25d51d3e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/22/2018
---
# <a name="globalization-and-localization-of-excel-solutions"></a>Genelleştirme ve yerelleştirme Excel çözümleri
  Bu bölüm, Windows için İngilizce olmayan ayarlara sahip bilgisayarlarda çalışan Microsoft Office Excel çözümleri için özel konular hakkında bilgi içerir. Visual Studio kullanarak çözümleri diğer tür oluşturduğunuzda karşılaştığınız çoğu yönlerini Genelleştirme ve Microsoft Office Çözümlerini Yerelleştirme aynı olduğunu. Genel bilgi için bkz: [Globalize ve uygulamaları yerelleştirme](/visualstudio/ide/globalizing-and-localizing-applications).  
  
 Varsayılan olarak, Microsoft Office Excel çalışma ana bilgisayar denetimleri doğru tüm Windows bölgesel ayarında geçirilen veya kullanarak yönetilen tüm verileri yönetilen kodu sürece biçimlendirilmiş biçimlendirme İngilizce (ABD) kullanarak. ' İ hedefleyen projelerde [!INCLUDE[net_v40_short](../sharepoint/includes/net-v40-short-md.md)] veya [!INCLUDE[net_v45](../vsto/includes/net-v45-md.md)], bu davranış ortak dil çalışma zamanı tarafından (CLR) denetlenir.  
  
 [!INCLUDE[appliesto_xlalldocapp](../vsto/includes/appliesto-xlalldocapp-md.md)]  
  
## <a name="format-data-in-excel-with-various-regional-settings"></a>Excel verileri biçimlendirme çeşitli bölgesel ayarlarla  
 Yerel ayara duyarlı, tarihleri ve para birimi, daha önce İngilizce (ABD) veri biçimi (yerel ayar kimliği 1033) kullanarak, gibi Microsoft Office Excel geçti veya Office projenizdeki kod verileri okuyabilir biçimlendirmeye sahip tüm verilerin biçimlendirilmesi gerekir.  
  
 Visual Studio'da Office çözümü geliştirirken, varsayılan olarak, Excel nesne modeli (Bu da yerel ayar kimliği 1033 nesne modeline kilitleme adlandırılır) yerel ayar kimliği 1033 veri biçimlendirmeyi bekliyor. Bu davranış, Visual Basic for Applications çalışır şekilde eşleşir. Ancak, Office çözümlerinde bu davranışı değiştirebilirsiniz.  
  
### <a name="understand-how-the-excel-object-model-always-expects-locale-id-1033"></a>Excel nesne modeline her zaman yerel ayar kimliği 1033 bekliyor nasıl anlama  
 Varsayılan olarak, Visual Studio kullanarak oluşturduğunuz Office çözümleri son kullanıcının yerel ayarları tarafından etkilenmez ve her zaman yerel ayarı İngilizce (ABD) olsa gibi davranır. Örneğin almak veya ayarlamak, <xref:Microsoft.Office.Interop.Excel.Range.Value2%2A> özelliğindeki, verileri yerel ayar kimliği 1033 bekliyor şekilde biçimlendirilmelidir. Farklı veri biçimi kullanıyorsanız, beklenmedik sonuçlar alabilirsiniz.  
  
 Geçirilen veya yönetilen kod tarafından yönetilen veriler için İngilizce (ABD) biçimini kullanıyor olsanız da Excel yorumlar ve verileri doğru son kullanıcının yerel ayarı göre görüntüler. Yönetilen kod yerel ayar kimliği 1033 verileri İngilizce (ABD) olduğunu gösterir verileri birlikte biçimi geçirir ve bu nedenle kullanıcının yerel ayarı eşleşecek şekilde yeniden biçimlendirilebileceği gerekir çünkü Excel verileri doğru şekilde biçimlendirebilirsiniz.  
  
 Son kullanıcılar için Almanca (Almanya) yerel ayar kendi Bölgesel Seçenekler varsa, örneğin, bu şekilde biçimlendirilmesi için tarih 29 Haziran 2005 bekledikleri: 29.06.2005. Ancak, çözümünüzün bir dize olarak Excel'e tarihini geçerse, İngilizce (ABD) biçimi göre tarihi biçimlendirmeniz gerekir: 29/6/2005. Hücre tarih hücre olarak biçimlendirilmiş olması gerekir, Excel tarihi Almanca (Almanya) biçiminde görüntüler.  
  
### <a name="pass-other-locale-ids-to-the-excel-object-model"></a>Excel nesne modeline diğer yerel ayar kimlikleri geçirin  
 Ortak dil çalışma zamanı (CLR) tüm yöntemler ve yerel ayara duyarlı verileri kabul Excel nesne modeline özelliklerinde 1033 yerel ayar Kimliğini otomatik olarak geçirir. Nesne modeline tüm çağrıları için otomatik olarak bu davranışı değiştirmek için bir yolu yoktur. Belirli bir yöntemi kullanarak farklı yerel ayar kimliği ancak geçirebilirsiniz <xref:System.Type.InvokeMember%2A> yöntemini çağırmak için ve yerel ayar kimliği geçirerek *kültür* yönteminin parametresi.  
  
## <a name="localize-document-text"></a>Belge metni yerelleştirme  
 Büyük olasılıkla belge, şablon veya projenizdeki çalışma kitabının derlemesinden ayrı olarak yerelleştirilmiş ve diğer yönetilen kaynaklar olmalıdır statik metin içerir. Bunu yapmak için basit bir yol, belgenin bir kopyasını yapmak ve Microsoft Office Word veya Microsoft Office Excel kullanarak metin Çevir eklemektir. Kod, hiçbir değişiklik olsa bile bu işlem belgeleri herhangi bir sayıda aynı derlemeye bağlanabileceğinden çalışır.  
  
 Hala belge metni ile etkileşime giren kodunuzu herhangi bir kısmını metni ve adlandırılmış aralıkları, bu yer işaretleri dilini eşleşecek şekilde devam eder ve tüm gerekli Office belgenin biçimlendirme diğer görüntü alanları uyum emin olmanız gerekir farklı dilbilgisi ve metin uzunluğu için ayarlayın. Görece küçük metin içeren belge şablonları için metni kaynak dosyalarını depolamak ve çalışma zamanında metin yüklenirken düşünmek isteyebilirsiniz.  
  
### <a name="text-direction"></a>Metin yönü  
 Excel'de sağdan sola metin işlemek için çalışma özelliği ayarlayabilirsiniz. Konak denetimleri veya sahip herhangi bir denetimi bir `RightToLeft` designer'ı otomatik olarak yerleştirilir özelliği, bu ayarlar çalışma zamanında eşleşmesi. Word (hemen değiştirdiğinizde, metin hizalamasını) çift yönlü metin için bir belge ayarı yok denetimleri için bu ayarı eşlenemez şekilde. Bunun yerine, her denetim için metin hizalamasını ayarlamanız gerekir. Tüm denetimler izlemek ve bunları sağdan sola metinden işlemek için zorlamak için kod yazma mümkündür.  
  
### <a name="change-culture"></a>Kültür değiştirme  
 İş parçacığı kültürünü yaptığınız tüm değişiklikler etkiler şekilde o iş parçacığı üzerinde çalışan her belge düzeyi özelleştirme kodunuz ana kullanıcı Arabirimi iş parçacığı Excel, genellikle paylaşır; Değiştir özelleştirmeyi için sınırlı değildir.  
  
 Windows Forms denetimleri, uygulama düzeyinde VSTO eklentileri konak uygulama tarafından başlatılan önce başlatılır. Kullanıcı Arabirimi denetimlerini ayarlamadan önce bu durumda, kültür değiştirilmesi gerekir.  
  
## <a name="install-the-language-packs"></a>Dil paketlerini yükleyin  
 Windows için İngilizce olmayan ayarları varsa, yükleyebileceğiniz [!INCLUDE[vsto_runtime](../vsto/includes/vsto-runtime-md.md)] görmek için dil paketlerini [!INCLUDE[vsto_runtime](../vsto/includes/vsto-runtime-md.md)] Windows ile aynı dilde iletileri. Herhangi bir son kullanıcı, Windows için İngilizce olmayan ayarlarla çözümlerinizi çalıştırırsanız, bunlar Windows çalışma zamanı iletilerini aynı dilde görmek için doğru dil paketi yüklü olmalıdır. [!INCLUDE[vsto_runtime](../vsto/includes/vsto-runtime-md.md)] Dil paketleri kullanılabilir [Microsoft Yükleme Merkezi'nden](http://www.microsoft.com/downloads).  
  
 Ayrıca, yeniden dağıtılabilir .NET Framework dil paketleri için ClickOnce iletileri gereklidir. .NET Framework dil paketleri mevcuttur [Microsoft Yükleme Merkezi'nden](http://www.microsoft.com/downloads).  
  
## <a name="regional-settings-and-excel-com-calls"></a>Bölgesel ayarları ve Excel COM çağrıları  
 Yönetilen bir istemci bir COM nesnesi üzerinde bir yöntemi çağırır ve kültüre özgü bilgileri geçirmek gereken zaman, bunu kullanarak mevcut <xref:System.Globalization.CultureInfo.CurrentCulture%2A> (yerel), geçerli iş parçacığı yerel ayar eşleşir. Geçerli iş parçacığı yerel ayarı kullanıcının bölgesel ayarları varsayılan olarak devralınır. Ancak, Excel nesne modeline çağrı Visual Studio'da Office geliştirme araçları kullanılarak oluşturulmuş bir Excel çözümden yaptığınızda, İngilizce (ABD) veri biçimi (yerel ayar kimliği 1033) Excel nesne modeline otomatik olarak geçirilir. İngilizce (ABD) veri biçimi, Microsoft Office Excel geçirin veya veri proje kodunuzdan okumadan önce kullanma tarihleri ve para birimi, gibi yerel ayara duyarlı biçimlendirmeye sahip tüm verileri biçimlendirmeniz gerekir.  
  
## <a name="considerations-for-storing-data"></a>Veri depolamak için dikkat edilecek noktalar  
 Verilerinizi doğru yorumlanması ve görüntülenen, bir uygulama içinde dize değişmez değerleri Excel çalışma sayfası formülleri gibi veri depolarken sorunlar oluşabilir de dikkate almalısınız emin olmak için (sabit yerine türü kesin belirlenmiş nesnelerin kodlanmış). Bir kültür değişmeyen veya İngilizce (Birleşik Devletler)) (LCID değeri 1033) stili varsayılarak biçimlendirilmiş verilerin kullanmanız gerekir.  
  
### <a name="applications-that-use-string-literals"></a>Dize değişmez değerleri kullanan uygulamalar  
 Sabit kodlanmış olabilir olası değerler İngilizce (ABD) biçimi ve yerelleştirilmiş işlev adları içeren Excel çalışma sayfası formülleri yazılır tarih değişmez değerleri içerir. Diğer bir olasılık "1000"; gibi bir sayı içeren sabit kodlanmış bir dize olabilir Bazı kültürler Bu bin yorumlanır, ancak diğer kültürler bir noktası sıfır temsil eder. Hesaplamalar ve yanlış biçim gerçekleştirilen karşılaştırmaları hatalı veri kaybına neden.  
  
 Excel geçirilen LCID uygun herhangi bir dizgi dizesiyle yorumlar. Dize biçimi geçirilen LCID karşılık gelmiyorsa bu bir sorun olabilir. Excel çözümlerini Visual Studio'da Office geliştirme araçlarını kullanarak oluşturduğunuz tüm veri geçirme LCID 1033'tür (en-US) kullanın. Excel verileri Excel kullanıcı arabirimi dil ve bölgesel ayarları göre görüntüler. Visual Basic for Applications (VBA) de bu şekilde çalışır; dizeleri en-US biçimlendirilmiş ve VBA, neredeyse her zaman 0 (dilden) LCID geçirir. Örneğin, aşağıdaki VBA kodu geçerli kullanıcı yerel ayarı uygun olarak 12 Mayıs 2004 için doğru biçimlendirilmiş bir değer görüntüler:  
  
```  
'VBA  
Application.ActiveCell.Value2 = "05/12/04"  
```  
  
 Tarih en-US stilde biçimlendirildiğinde aynı kodu Visual Studio'da Office geliştirme araçları kullanılarak oluşturulan ve COM birlikte çalışma ile Excel'e geçirilen bir çözüm kullanıldığında, aynı sonucu verir.  
  
 Örneğin:  
  
 [!code-vb[Trin_VstcoreCreatingExcel#6](../vsto/codesnippet/VisualBasic/Trin_VstcoreCreatingExcelVB/Sheet1.vb#6)]
 [!code-csharp[Trin_VstcoreCreatingExcel#6](../vsto/codesnippet/CSharp/Trin_VstcoreCreatingExcelCS/Sheet1.cs#6)]  
  
 Kesin türü belirtilmiş veri dize değişmez değerleri mümkün olduğunda yerine ile çalışması gerekir. Örneğin, bir dize sabit değeri bir tarih depolamak yerine olarak depolamak bir <xref:System.Double>, ardından dönüştürün bir <xref:System.DateTime> işleme için nesnesi.  
  
 Aşağıdaki kod örneği, bir kullanıcı hücreye A5 girer, bunları olarak depolayan bir tarih kazanır bir <xref:System.Double>, kendisine dönüştürür bir <xref:System.DateTime> hücre A7 görüntülemek nesnesi. Bir tarih görüntülenecek hücre A7 biçimlendirilmiş olması gerekir.  
  
 [!code-vb[Trin_VstcoreCreatingExcel#7](../vsto/codesnippet/VisualBasic/Trin_VstcoreCreatingExcelVB/Sheet1.vb#7)]
 [!code-csharp[Trin_VstcoreCreatingExcel#7](../vsto/codesnippet/CSharp/Trin_VstcoreCreatingExcelCS/Sheet1.cs#7)]  
  
### <a name="excel-worksheet-functions"></a>Excel çalışma sayfası işlevleri  
 Çalışma sayfası işlevi adları Excel çoğu dil sürümleri için dahili olarak çevrilir. Ancak, olası dil ve COM birlikte çalışma sorunları nedeniyle kodunuzda yalnızca İngilizce işlev adlarını kullanmanız önerilir.  
  
### <a name="applications-that-use-external-data"></a>Dış veri kullanan uygulamalar  
 Bu tür dosyaları en-US yanı sıra herhangi bir biçimini kullanarak verilirse açar veya aksi halde eski bir sistemden dışarı virgülle ayrılmış değerler (CSV dosyaları) dosyaları gibi dış veri kullanan herhangi bir kod da etkilenebilir. Veritabanı dize olarak tarihleri saklar veya ikili biçimi kullanmayın işlemleri gerçekleştirir sürece tüm değerleri ikili dosya biçiminde olması gerektiğinden veritabanı erişimi etkilenen değil. Ayrıca, Excel verilerini kullanarak SQL sorguları oluşturmak, kullandığınız işlevi bağlı olarak, en-US biçiminde olduklarından emin olmak gerekebilir.  
  
## <a name="see-also"></a>Ayrıca bkz.  
 [Nasıl yapılır: Office Çok Dilde Kullanıcı arabirimini hedefleme](../vsto/how-to-target-the-office-multilingual-user-interface.md)   
 [Tasarlama ve Office çözümleri oluşturma](../vsto/designing-and-creating-office-solutions.md)   
 [Office çözümlerinde isteğe bağlı parametreler](../vsto/optional-parameters-in-office-solutions.md)  
  
  