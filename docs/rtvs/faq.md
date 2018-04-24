---
title: R araçları Visual Studio ile ilgili SSS
description: Visual Studio'da R hakkında sık sorulan sorular.
ms.date: 12/04/2017
ms.prod: visual-studio-dev15
ms.technology: vs-rtvs
ms.topic: reference
author: kraigb
ms.author: kraigb
manager: douge
ms.workload:
- data-science
ms.openlocfilehash: a8b9dd119aba9a5c28b450db11b2eb380b1872a0
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/19/2018
---
# <a name="frequently-asked-questions"></a>Sık sorulan sorular

## <a name="visual-studio-support"></a>Visual Studio desteği

**Q. RTVS, OS X veya Linux üzerinde çalışıyor mu?**

BİR. RTVS şu anda yalnızca Windows uygulaması olan Visual Studio üzerinde oluşturulmuştur. Microsoft Visual Studio Code ve Visual Studio for Mac desteğini araştırmaktadır. Başvurmak [RTVS sorun #1295](https://github.com/Microsoft/RTVS/issues/1295).

**Q. RTVS Visual Studio Express sürümleri ile çalışır mı?**

BİR. Hayır.

**Q. Visual Studio uzantıları ile RTVS kullanabilir miyim?**

BİR. Kesinlikle. Aslında, popüler kişiler r ile çalışmak için birkaç İşte

- [VsVim VIM anahtar bağlamaları için](https://marketplace.visualstudio.com/items?itemName=JaredParMSFT.VsVim)
- [Github](https://marketplace.visualstudio.com/items?itemName=GitHub.GitHubExtensionforVisualStudio)
- [Markdown Düzenleyicisi ile Canlı Önizleme](https://marketplace.visualstudio.com/items?itemName=MadsKristensen.MarkdownEditor)

Bkz: [Visual Studio Market'te](https://marketplace.visualstudio.com/) daha fazla bulunamıyor.

**Q. Visual Studio'da RTVS olduğu için R kolayca C#, C++ ve diğer Microsoft dillerle kullanılabilir olduğunu anlama geliyor?**

BİR. Hayır. RTVS R kodu geliştirmek için bir araçtır ve standart yerel R yorumlayıcılar kullanır. R ve diğer diller arasında birlikte şu anda desteklenmiyor.

**Q. RTVS İngilizce dışındaki yerel ayar ile çalışır mı?**

BİR. RTVS 1.0 sürümünde yalnızca İngilizce. 1.1 sürüm Visual Studio kendisini dilleri aynı kümesine yerelleştirilmiş. Bu arada, kullanın [İngilizce dil paketi Visual Studio 2015 için](https://www.microsoft.com/download/details.aspx?id=48157), ya da Visual Studio 2017 içinde yükleyiciyi çalıştırın ve İngilizce seçin **dil paketlerini** sekmesi.

![Visual Studio 2017 için uluslararası ayarları](media/FAQ-international-settings.png)

**Q. I gerçekten geçerli Visual Studio ayarlarımı gibi çalışır, ancak yeni veri bilimi ayarları istiyor. Ne yapmalıyım?**

BİR. Geçerli Visual Studio ayarlarınızı kullanarak kaydetmek **Araçlar > içeri ve dışarı aktarma ayarları...** , veri bilimi ayarlarına geçiş yapın. Kaydedilmiş ayarları geri yüklemek için kullanmak **içeri ve dışarı aktarma ayarları...**  yeniden komutu.

**Q. Visual Studio Proje bir ağ paylaşımında depolayabilir miyim?**

BİR. Hayır, Visual Studio yükleme projeleri bir ağ paylaşımından desteklemiyor.

## <a name="r-interpretersintegration"></a>R yorumlayıcılar/tümleştirme

**Q. Hangi R yorumlayıcılar RTVS ile çalışır mı?**

BİR. [CRAN R](https://cran.r-project.org/), [Microsoft R istemci ve Microsoft Server öğrenme makinesi](/machine-learning-server/)

**Q. Bu yorumlayıcılar nereden indirebilirim?**

BİR. Bkz: [yükleme](installing-r-tools-for-visual-studio.md).

Q **Microsoft R Server nedir?**

BİR. R Server adıdır eski [Microsoft Machine Learning sunucusu](/machine-learning-server/what-is-machine-learning-server).

**Q. RTVS R 32 bit sürümleri ile çalışır mı?**

BİR. Hayır, RTVS yalnızca R Windows 64-bit sürümlerini çalıştıran 64 bit sürümleri destekler.

**Q. RTVS my kaynak denetim sistemi ile çalışır mı?**

BİR. Evet, Visual Studio'ya tümleşik tüm kaynak denetim sistemi kullanabilirsiniz.

**Q. Önerilen nelerdir `.gitignore` RTVS proje ayarlarını?**

BİR. Github tutar, ana depo önerilen `.gitignore` dosyaları. Burada görebilirsiniz: [R .gitignore](https://github.com/github/gitignore/blob/master/R.gitignore)

## <a name="remote-services"></a>Uzak Hizmetleri

Q. **Visual Studio'da uzaktan Hizmetleri nedir?**

BİR. Visual Studio için Uzak R Hizmetleri, Windows veya Linux makine kurun ve ardından RTVS bağlanmak olanak sağlar. Bkz: [uzak çalışma alanları ayarlama](setting-up-remote-r-workspaces.md).

Q. **RTVS Microsoft R sunucusuna bağlanabiliyor musunuz?**

BİR. Hayır, Microsoft R Server farklı bir teknolojidir ve aynı bağlantı mekanizması olarak sağlamaz çünkü RTVS tarafından gerekli.

Q. **Azure üzerinde veri bilimi VM görüntüsü kullanılarak oluşturulan VM RTVS bağlanabiliyor musunuz?**

BİR. Evet; [veri bilimi VM - Windows 2016](https://azure.microsoft.com/services/virtual-machines/data-science-virtual-machines/) görüntü Visual Studio için uzaktan R Hizmetleri'yle önceden yüklenmiş olarak gelir.

Q, **yapabilirsiniz RTVS yüklü R ile uzak makineye bağlanmak?**

Var olan bazı hizmet isteklerini dinlemek için uzak makinede R kod yürütmek için kodu alma ve sonuçları gönderme için istemci makine yedekleyin. Visual Studio için Uzak R Hizmetleri ne budur. Bkz: [uzak çalışma alanları ayarlama](setting-up-remote-r-workspaces.md).

Q. **Uzak oturum nedir?**

BİR. Makalesine bakın [uzak sunucuda yürütme](/machine-learning-server/r/how-to-execute-code-remotely) Machine Learning Server belgelerinde.

## <a name="rtvs-development-and-features"></a>RTVS geliştirme ve özellikleri

**Q. Özellik X eksik, ancak Rstudio'dan sahiptir!**

BİR. Rstudio'dan harika ve olgun IDE yıllardır için geliştirilmekte olan r ' dir. Başarılı olması için gereken tüm kritik özelliklerine sahip getirmeye RTVS çalışır. Gelecekteki iş gerçekleştirerek öncelik Yardım [RTVS anket](https://www.surveymonkey.com/r/RTVS1) ve dosya sorunları [GitHub](https://github.com/Microsoft/RTVS/issues/).

**Q. İçin RTVS katkıda bulunabilirsiniz?**

BİR. Kesinlikle! Kaynak kodu yaşamaktadır [Github](https://github.com/microsoft/RTVS). Hataları gönderme ve zaten Dosyalanan üzerindekiler açıklama sorun İzleyicisi'ni kullanın.

Ayrıca bu belgelerine katkıda bulunma Hoş Geldiniz&mdash;yalnızca select **Düzenle** sağ üst tarafındaki herhangi bir sayfa üzerinde komutu. Belgeleri açıklamaları Ayrıca, herhangi bir sayfanın alt kısmında ekleyebilirsiniz Hoş Geldiniz.
