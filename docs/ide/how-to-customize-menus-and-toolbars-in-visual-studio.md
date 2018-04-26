---
title: 'Nasıl yapılır: menüleri ve Visual Studio içinde araç çubuklarını özelleştirme'
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-general
ms.topic: conceptual
f1_keywords:
- vs.renametoolbar
- vs.customize.toolbars
- vs.buttoneditor
- vs.customize.commands
- vs.newtoolbar
helpviewer_keywords:
- captions, customizing toolbar
- custom toolbars [Visual Studio]
- command buttons, customizing toolbar
- labels, customizing toolbar
- images [Visual Studio], toolbar buttons
- buttons [Visual Studio], custom toolbars
- toolbars [Visual Studio], creating in the IDE
- icons [Visual Studio], customizing toolbar
- commands [Visual Studio], customizing environment
- customizing toolbars
- toolbars [Visual Studio], customizing
- toolbars [Visual Studio], customizing in the IDE
ms.assetid: b570ae2f-5302-45dc-9cc9-8d4d1ad50603
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 6400f1d501ef6a89a6f98cf040d2f729469ccf71
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/26/2018
---
# <a name="how-to-customize-menus-and-toolbars-in-visual-studio"></a>Nasıl yapılır: menüleri ve Visual Studio içinde araç çubuklarını özelleştirme

Visual Studio yalnızca araç çubukları ve menü çubuğunda menüleri ekleyerek veya kaldırarak, ancak aynı zamanda tarafından ekleme ve kaldırma verilen araç veya menü komutlarını özelleştirebilirsiniz.

> [!WARNING]
> Araç çubuğu veya menü özelleştirdikten sonra onay kutusu içinde seçilen kaldığından emin olun **Özelleştir** iletişim kutusu. Aksi takdirde, Visual Studio'yu kapatıp yeniden açtıktan sonra değişiklikleriniz kalıcı olmaz.

## <a name="add-remove-or-move-a-menu-on-the-menu-bar"></a>Eklemek, kaldırmak veya menü çubuğunda bir menü taşıma

1.  Menü çubuğunda seçin **Araçları** > **Özelleştir**.

     **Özelleştir** iletişim kutusu açılır.

2.  Üzerinde **komutları** sekmesinde, bırakın **menü çubuğu** seçenek düğmesi seçiliyken, bırakın **menü çubuğu** seçeneği yanındaki listesinde seçili ve aşağıdaki adımlardan birini gerçekleştirin adımlar:

    -   Menü eklemek için **yeni menü ekleme** düğmesini tıklatın, seçin **Seçimi Değiştir** düğmesine tıklayın ve ardından eklemek istediğiniz menü adı.

        ![Özelleştir iletişim kutusu bir menü ekleme gösteren](../ide/media/addmenu.png "MenüEkle")

    -   Bir menüyü kaldırmak için bunu seçin **denetimleri** listeleyin ve ardından **silmek** düğmesi.

    -   Menü çubuğu içinde menüyü taşımak için menüsünde seçin **denetimleri** listeleyin ve ardından **Yukarı Taşı** veya **Aşağı Taşı** düğmesi.

## <a name="add-remove-or-move-a-toolbar"></a>Eklemek, kaldırmak veya bir araç çubuğu taşıma

1.  Menü çubuğunda seçin **Araçları** > **Özelleştir**.

     **Özelleştir** iletişim kutusu açılır.

2.  Üzerinde **araç** sekmesinde, aşağıdaki adımlardan birini gerçekleştirin:

    -   Araç çubuğu eklemek için **yeni** düğmesini tıklatın, eklemek ve ardından istediğiniz araç için bir ad belirtin **Tamam** düğmesi.

        ![Özelleştir iletişim kutusu bir araç eklemek nasıl gösteren](../ide/media/addtoolbar.png "AddToolbar")

    -   Özel bir araç çubuğu kaldırmak için bunu seçin **araç çubukları** listeleyin ve ardından **silmek** düğmesi.

        > [!IMPORTANT]
        > Kendi oluşturduğunuz araç çubuklarını silebilir, ancak varsayılan araç çubuklarını silemezsiniz.

    -   Araç çubuğu yerleştirme farklı bir konuma taşımak için bunu seçin **araç çubukları** listesinde, seçin **Seçimi Değiştir** düğmesine tıklayın ve sonra görüntülenen listede bir konum seçin.

        Ayrıca, bir araç çubuğunu, ana yerleştirme alanında herhangi bir konuma taşımak için sol kenarından sürükleyebilirsiniz.

        > [!NOTE]
        > Kullanılabilirlik ve araç çubuklarını erişilebilirliğini geliştirme konusunda daha fazla bilgi için bkz: [nasıl yapılır: ayarlama IDE erişilebilirlik seçeneklerini](../ide/reference/how-to-set-ide-accessibility-options.md).

## <a name="customizing_menu">Menü veya araç çubuğunu özelleştirme</a>

1.  Menü çubuğunda seçin **Araçları** > **Özelleştir**.

    **Özelleştir** iletişim kutusu açılır.

2.  Üzerinde **komutları** sekmesinde, özelleştirmek istediğiniz öğe türü için seçenek düğmesini seçin.

3.  Bu öğe türüne ilişkin listede, özelleştirmek istediğiniz menü veya araç çubuğunu seçin ve sonra aşağıdaki adım gruplarından birini gerçekleştirin:

    -   Bir komut eklemek için **Add komutunu** düğmesi.

        İçinde **Add komutunu** iletişim kutusunda, bir öğe seçin **kategorileri** listesinde, bir öğe seçin **komutları** listeleyin ve ardından **Tamam**düğmesi.

        ![Visual Studio'da Ekle komutu iletişim kutusu](../ide/media/addcommand.png "AddCommand")

    -   Bir komut silmek için bunu seçin **denetimleri** listeleyin ve ardından **silmek** düğmesi.

    -   Komutları yeniden sıralamak için bir komut seçin **denetimleri** listeleyin ve ardından **Yukarı Taşı** veya **Aşağı Taşı** düğmesi.

    -   Komutlar yatay çizgi altında gruplandırmak için ilk komutu seçin **denetimleri** listesinde, seçin **Seçimi Değiştir** düğmesine tıklayın ve ardından **Grup Başlat** içinde görünen menüsü.

## <a name="reset-a-menu-or-a-toolbar"></a>Menü veya araç Sıfırla

1.  Menü çubuğunda seçin **Araçları** > **Özelleştir**.

    **Özelleştir** iletişim kutusu açılır.

2.  Üzerinde **komutları** sekmesinde, sıfırlamak istediğiniz öğe türü için seçenek düğmesini seçin.

3.  Bu öğe türüne ilişkin listede, sıfırlamak istediğiniz menü veya araç çubuğunu seçin.

4.  Seçin **Seçimi Değiştir** düğmesine tıklayın ve ardından **sıfırlama** menüde görünür.

    Seçerek tüm menüleri ve araç çubuklarını da sıfırlayabilirsiniz **Tümünü Sıfırla** düğmesi.

## <a name="see-also"></a>Ayrıca bkz.

- [IDE'yi kişiselleştirme](../ide/personalizing-the-visual-studio-ide.md)
- [Düzenleyiciyi özelleştirme](../ide/customizing-the-editor.md)