---
title: Git ile çalışma
description: Git Mac için Visual Studio kullanarak
author: asb3993
ms.author: amburns
ms.date: 05/06/2018
ms.assetid: 852B6A9D-AEFA-4EF4-A5DD-94A506019D20
ms.openlocfilehash: a63e954b2f7998e334c94221186907963540d329
ms.sourcegitcommit: 33c954fbc8e05f7ba54bfa2c0d1bc1f9bbc68876
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/08/2018
---
# <a name="working-with-git"></a>Git ile çalışma

Git takımlar aynı belgelerde aynı anda çalışmasına izin veren bir dağıtılmış sürüm denetim sistemidir. Bu, tüm dosyaları içeren bir merkezi sunucu yoktur, ancak bir depo merkezi bu kaynaktan kullanıma alındığında, tüm depo yerel makine kopyalanmış anlamına gelir.

Aşağıdaki bölümler nasıl Git sürüm denetimi Visual Studio için Mac için kullanılabileceğini keşfedin

## <a name="git-version-control-menu"></a>Git Sürüm Denetim menüsü

Aşağıdaki görüntü, Visual Studio tarafından Mac için sürüm denetimi menü öğesi tarafından sağlanan seçenekleri gösterilmektedir:

![Sürüm denetimi menü öğesi](media/version-control-gitVersionControlMenu.png)

## <a name="push-and-pull"></a>İtme ve çekme 

İletme ve çekme Git içinde en yaygın kullanılan eylemler ikisidir. Diğer kişilerin Uzak depoya yapmış olduğunuz değişiklikleri eşitlemek için şunları yapmalısınız **çekme** buradan. Bu seçerek Mac için Visual Studio'da yapılır **sürüm denetimi > güncelleştirme çözümü**.

Dosyalarınızı güncelleştirildi, gözden geçirdikten ve bunları kabul edilen sonra ardından gerekir **anında** onları başkalarının değişikliklerinizi erişmesine izin vermek için Uzak depo. Bu seçerek Mac için Visual Studio'da yapılır **sürüm denetimi > anında değişiklikleri**. Bu, yapılan değişiklikleri görüntülemenizi sağlayan anında iletişim kutusunu görüntülemek ve iletin dalı seçin:

![İletişim için yürütmek için şube gösterme](media/version-control-gitPush.png)

Ayrıca kaydetmek ve aynı zamanda, yürütme iletişim aracılığıyla değişikliklerinizi gönderme:

![Yürütme ve gönderme nasıl gösteren seçeneği aynı zamanda.](media/version-control-commitPush.png)

## <a name="blame-log-and-merge"></a>, Günlük, nedenlerle ve birleştirme

Pencerenin alt kısmındaki vardır, beş sekmeleri aşağıda gösterildiği gibi:

![Sürüm denetimi sekmeleri](media/version-control-gitTabs.png)

Bunlar, aşağıdaki eylemleri izin ver:

* **Kaynak** -kaynak kodu dosyasının görüntüler.
* **Değişiklikleri** -yerel dosyanızı ve temel dosyanın arasında kodda değişiklik görüntüler. Ayrıca, farklı dosya sürümlerinden farklı karmaları karşılaştırabilirsiniz:

    ![Değişiklikleri sekmesi](media/version-control-gitChange.png)

* **Nedenlerle** -her bir kod bölümle ilişkili kullanıcı adını görüntüler.
* **Günlük** -tüm işlemeleri, saat, tarih, iletileri ve dosyayı sorumlu olan kullanıcılar görüntüler:

    ![Günlük Sekmesi](media/version-control-gitLog.png)

* **Birleştirme** -çalışmanızı yürüten alırken bir birleştirme çakışması varsa, bu kullanılabilir. Görsel bir siz ve, her iki kod bölümlerini düzgün bir şekilde birleştirmenize izin vererek diğer geliştiricisi tarafından yapılan değişiklikleri gösterir. 

## <a name="switching-branches"></a>Dalları değiştirme 

Varsayılan olarak, bir depoda oluşturulan ilk dal olarak bilinir **ana** dal. Hiç teknik ana dala ve diğer arasında farklı bir şey, ancak ana dala çoğunlukla, geliştirme ekiplerinin 'Canlı' veya 'üretim' dal olarak düşünüldüğü adrestir.

Geliştirme bağımsız bir satırın asıl (veya herhangi başka bir dal, bu) devre dışı dallara ayırma tarafından oluşturulabilir. Bu ana dala bir noktada yeni bir sürümü 'Canlı.' nedir bağımsız olarak geliştirme için izin vererek, zaman içindeki sağlar Bu şekilde dalları kullanmak genellikle yazılım geliştirme özellikleri için kullanılır

Kullanıcılar için her depo istiyor, ancak bir dal kullanmayı bitirdikten sonra bu silinir önerilir kadar dala oluşturabilirsiniz depo tutmak için düzenlenmiştir.

Dalları görüntülendiğinde Visual Studio'da Mac için göz atarak **sürüm denetimi > dal yönetme ve uzaktan kumandalar...** :

![Dalları görüntüle](media/version-control-gitBranch2.png)

Geçiş için başka bir şube listesi ve tuşlarına basarak seçerek **geçiş dala** düğmesi.

Yeni bir şube select oluşturmak için **yeni** Git deposu yapılandırma iletişim düğmesini. Yeni şube adı girin:

![Yeni dal oluşturma](media/version-control-gitBranch.png)

De bir uzak şube ayarlayabilirsiniz, _izleme_ dal. Dallarda izleme hakkında daha fazla okuma [Git belgelerine](https://git-scm.com/book/en/v2/Git-Branching-Remote-Branches#Tracking-Branches).

Proje adının yanındaki çözüm panelinde geçerli dal bakın:

 ![Çözüm panelinde görüntülenen geçerli dal](media/version-control-gitBranchName.png)

## <a name="reviewing-and-committing"></a>Gözden geçirme ve teslim etme 

Dosyalardaki değişiklikler gözden geçirmek için değişiklikleri, nedenlerle, günlük kullanın ve bu konunun önceki bölümlerinde gösterilen her bir belgenin sekmelerinde birleştirme.

Göz atarak projenizdeki tüm değişiklikleri gözden **sürüm denetimi > gözden geçirme çözüm ve yürütme** menü öğesi:

![Kod Görünümü gözden geçirin](media/version-control-gitReviewCommit.png)

Bu, bir projenin geri, bir düzeltme eki oluşturma veya Yürüt seçeneğine sahip her bir dosyadaki tüm değişiklikleri görüntülenmesini sağlar.

Bir dosyayı uzak depoya tamamlamaya basın **tamamlama...** kaydetme iletisi girin ve yürütme düğmesi ile onaylayın:

![Bir dosya teslim etme](media/version-control-gitCommit.png)

Yaptığınız değişiklikleri tamamladıktan sonra bunları diğer kullanıcıların görebileceği izin vermek için Uzak deponuza iletin.