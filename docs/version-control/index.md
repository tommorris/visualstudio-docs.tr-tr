---
layout: LandingPage
title: "Visual Studio'daki sürüm denetimi | VSTS & TFS"
description: "Sürüm denetimi Viual Studio'da ile Başlarken için kılavuz"
keywords: "VSTS, TFS, sürüm denetimi"
author: steved0x
ms.manager: douge
ms.author: sdanie
ms.date: 12/15/2017
ms.topic: landing-page
ms.prod: .net-core
ms.assetid: 2c119a5f-0272-48c0-8d6c-806196944aea
ms.workload:
- multiple
ms.openlocfilehash: 428139af8680bc60f4456367d1a17d4c97874efc
ms.sourcegitcommit: 39c525ec200c6c4ea94815567b3fad7ab14fb7b3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/08/2018
---
# <a name="version-control-in-visual-studio"></a>Visual Studio'daki sürüm denetimi

Sürüm denetim sistemleri zamanla kod değişiklikleri izlemenize yardımcı olur. Değişiklik yapmak gibi sürüm denetimi sistemi bir dosyalarınızın anlık görüntüsünü alır. Sürüm denetimi sistemi ihtiyacınız olursa, bunu daha sonra geri çağırma şekilde bu anlık görüntü kalıcı olarak kaydeder. Visual Studio sağlar [Git](/vsts/git/index) ve [Team Foundation sürüm denetimi (TFVC'yi)](/vsts/tfvc/index). İki sistem arasında karar vermek için bkz: [projeniz için doğru sürüm denetimi seçme](/vsts/tfvc/comparison-git-tfvc?toc=/visualstudio/version-control/toc.json&bc=/vsts/git/breadcrumb/vc/toc.json).

## <a name="git"></a>Git
Git en yaygın kullanılan sürüm denetimi sistemi bugün ise ve sürüm denetimi için standart hızla büyüyor. Git bir dağıtılmış sürüm denetim sistemi kodu yerel kopyasını bir tam sürüm denetimi depodur anlamına gelir. Çevrimdışı veya uzaktan çalışmak kolayca bu tam olarak işlevsel yerel depoları olun. Çalışmanızı yerel olarak kaydetmek ve depo kopyanızı sunucudaki kopyayla eşitleme. Bu örneği burada istemcileri kod bir sunucuyla kod yeni sürümlerini oluşturmadan önce eşitlenmelidir merkezi sürüm denetimi farklıdır.

<ul class="panelContent cardsFTitle">
    <li>
        <a href="https://www.visualstudio.com/learn-git/">
        <div class="cardSize">
            <div class="cardPadding">
                <div class="card">
                    <div class="cardImageOuter">
                        <div class="cardImage">
                            <img width="48" height="48" alt="" src="https://docs.microsoft.com/media/common/i_git-mark.svg" />
                        </div>
                    </div>
                    <div class="cardText">
                        <h3>Git kullanmayı öğrenin</h3>
                    </div>
                </div>
            </div>
        </div>
        </a>
    </li>
    <li>
        <a href="/vsts/git/share-your-code-in-git-vs-2017?toc=/visualstudio/version-control/toc.json&bc=/vsts/git/breadcrumb/vc/toc.json">
        <div class="cardSize">
            <div class="cardPadding">
                <div class="card">
                    <div class="cardImageOuter">
                        <div class="cardImage">
                            <img width="48" height="48" alt="" src="https://docs.microsoft.com/media/common/i_git-mark.svg" />
                        </div>
                    </div>
                    <div class="cardText">
                        <h3>Git ile Visual Studio ile çalışmaya başlama</h3>
                    </div>
                </div>
            </div>
        </div>
        </a>
    </li>
    <li>
        <a href="/vsts/git/tutorial/clone?toc=/visualstudio/version-control/toc.json&bc=/vsts/git/breadcrumb/vc/toc.json">
        <div class="cardSize">
            <div class="cardPadding">
                <div class="card">
                    <div class="cardImageOuter">
                        <div class="cardImage">
                            <img width="48" height="48" alt="" src="https://docs.microsoft.com/media/common/i_git-mark.svg" />
                        </div>
                    </div>
                    <div class="cardText">
                        <h3>Var olan bir Git deposuna kopyalama</h3>
                    </div>
                </div>
            </div>
        </div>
        </a>
    </li>
</ul>

## <a name="tfvc"></a>TFVC

Team Foundation Sürüm Denetimi (TFVC) merkezi sürüm denetim sistemidir. Genellikle, ekip üyeleri kendi geliştirme makinelerinde her dosyanın yalnızca bir sürümüne sahiptir. Geçmiş verisi yalnızca sunucuda tutulur. Dallar, yol tabanlıdır ve sunucuda oluşturulur.

<ul class="panelContent cardsFTitle">
    <li>
        <a href="/vsts/tfvc/overview">
        <div class="cardSize">
            <div class="cardPadding">
                <div class="card">
                    <div class="cardImageOuter">
                        <div class="cardImage">
                            <img width="48" height="48" alt="" src="https://docs.microsoft.com/media/logos/logo_visual-studio.svg" />
                        </div>
                    </div>
                    <div class="cardText">
                        <h3>TFVC'yi öğrenin</h3>
                    </div>
                </div>
            </div>
        </div>
        </a>
    </li>
    <li>
        <a href="/vsts/tfvc/share-your-code-in-tfvc-vs?toc=/visualstudio/version-control/toc.json&bc=/vsts/git/breadcrumb/vc/toc.json">
        <div class="cardSize">
            <div class="cardPadding">
                <div class="card">
                    <div class="cardImageOuter">
                        <div class="cardImage">
                            <img width="48" height="48" alt="" src="https://docs.microsoft.com/media/logos/logo_visual-studio.svg" />
                        </div>
                    </div>
                    <div class="cardText">
                        <h3>Visual Studio'da TFVC'yi kullanmaya başlama</h3>
                    </div>
                </div>
            </div>
        </div>
        </a>
    </li>
   <li>
        <a href="/vsts/tfvc/get-code-reviewed-vs?toc=/visualstudio/version-control/toc.json&bc=/vsts/git/breadcrumb/vc/toc.json">
        <div class="cardSize">
            <div class="cardPadding">
                <div class="card">
                    <div class="cardImageOuter">
                        <div class="cardImage">
                            <img width="48" height="48" alt="" src="https://docs.microsoft.com/media/logos/logo_visual-studio.svg" />
                        </div>
                    </div>
                    <div class="cardText">
                        <h3>Kodunuzu gözden geçirin</h3>
                    </div>
                </div>
            </div>
        </div>
        </a>
    </li>
</ul>


## <a name="resources"></a>Kaynaklar 

- [Pro Git rehberi](https://git-scm.com/book/en/v2)  
- [Git geçişinizi planlama](https://www.visualstudio.com/learn/centralized-to-git/)  
- [TFVC'yi geçirmek için Git](https://www.visualstudio.com/learn/migrate-from-tfvc-to-git/)  

 

