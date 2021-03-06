---
title: チュートリアル:Azure Active Directory と SAML SSO for Jira by resolution GmbH の統合 | Microsoft Docs
description: Azure Active Directory と SAML SSO for Jira by resolution GmbH の間でシングル サインオンを構成する方法について説明します。
services: active-directory
author: jeevansd
manager: CelesteDG
ms.reviewer: celested
ms.service: active-directory
ms.subservice: saas-app-tutorial
ms.workload: identity
ms.topic: tutorial
ms.date: 01/03/2018
ms.author: jeedes
ms.openlocfilehash: fe241a3fd74e1421f1bd3d39087fe776ee7b61d9
ms.sourcegitcommit: 4064234b1b4be79c411ef677569f29ae73e78731
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/28/2020
ms.locfileid: "92891586"
---
# <a name="tutorial-azure-active-directory-integration-with-saml-sso-for-jira-by-resolution-gmbh"></a>チュートリアル:Azure Active Directory と SAML SSO for Jira by resolution GmbH の統合

このチュートリアルでは、Azure Active Directory (Azure AD) で SAML SSO for Jira by resolution GmbH を設定する方法について説明します。
SAML SSO for Jira by resolution GmbH と Azure AD の統合には、次の利点があります。

* resolution GmbH による SAML SSO プラグインで Jira にサインインできるユーザーを Azure AD で制御できます。
* SAML SSO for Jira by resolution GmbH を使用することで、ユーザーが自分の Azure AD アカウントで Jira に自動的にサインインするように設定できます (シングル サインオン)。
* 1 つの中央サイト (Azure Portal) でアカウントを管理できます。

SaaS アプリと Azure AD の統合の詳細については、「 [Azure Active Directory のアプリケーション アクセスとシングル サインオンとは](../manage-apps/what-is-single-sign-on.md)」を参照してください。
Azure サブスクリプションをお持ちでない場合は、開始する前に[無料アカウントを作成](https://azure.microsoft.com/free/)してください。

## <a name="prerequisites"></a>前提条件

Azure AD の統合と SAML SSO for Jira by resolution GmbH を構成するには、次のものが必要です。

* Azure AD サブスクリプション。 Azure AD の環境がない場合は、[こちら](https://azure.microsoft.com/pricing/free-trial/)から 1 か月の試用版を入手できます
* SAML SSO for Jira by resolution GmbH でのシングル サインオンが有効なサブスクリプション

## <a name="scenario-description"></a>シナリオの説明

このチュートリアルでは、テスト環境で Azure AD のシングル サインオンを構成してテストします。

* SAML SSO for Jira by resolution GmbH では、 **SP** と **IDP** によって開始される SSO がサポートされます

## <a name="adding-an-enterprise-application-for-single-sign-on"></a>シングル サインオン用のエンタープライズ アプリケーションの追加

Azure AD でシングル サインオンを設定するには、新しいエンタープライズ アプリケーションを追加する必要があります。 ギャラリーには、これ用に事前構成済みのアプリケーション **SAML SSO for Jira by resolution GmbH** があります。

**ギャラリーから SAML SSO for Jira by resolution GmbH を追加するには、次の手順に従います。**

1. **[Azure Portal](https://portal.azure.com)** の左側のナビゲーション ウィンドウで、 **[Azure Active Directory]** アイコンをクリックします。

    ![Azure Active Directory のボタン](common/select-azuread.png)

2. **[エンタープライズ アプリケーション]** に移動し、 **[すべてのアプリケーション]** をクリックします。

    ![[エンタープライズ アプリケーション] ブレード](common/enterprise-applications.png)

3. 新しいアプリケーションを追加するには、ダイアログの上部にある **[新しいアプリケーション]** をクリックします。

    ![[新しいアプリケーション] ボタン](common/add-new-app.png)

4. [検索] ボックスに「 **SAML SSO for Jira by resolution GmbH** 」と入力し、結果パネルで **[SAML SSO for Jira by resolution GmbH]** を選び、 **[追加]** をクリックして、アプリケーションを追加します。 エンタープライズ アプリの名前を変更することもできます。

     ![結果一覧の SAML SSO for Jira by resolution GmbH](common/search-new-app.png)

## <a name="configure-and-test-single-sign-on-with-the-saml-sso-plugin-and-azure-ad"></a>SAML SSO プラグインと Azure AD でシングル サインオンを構成してテストする

このセクションでは、Azure AD ユーザー向けに Jira へのシングル サインオンを構成してテストします。 **Britta Simon** という名前のテスト ユーザーを使ってこれを行います。
シングル サインオンを機能させるには、Azure AD ユーザーと SAML SSO for Jira by resolution GmbH 内の関連ユーザーとの間にリンク関係が確立されている必要があります。

シングル サインオンを構成してテストするには、次の手順を完了する必要があります。

1. **[シングル サインオン用に Azure AD エンタープライズ アプリケーションを構成する](#configure-the-azure-ad-enterprise-application-for-single-sign-on)** - シングル サインオンのために Azure AD エンタープライズ アプリケーションを構成します
2. **[Jira インスタンスの SAML SSO プラグインを構成する](#configure-the-saml-sso-plugin-of-your-jira-instance)** - アプリケーション側でシングル サインオンの設定を構成します。
3. **[Azure AD のテスト ユーザーを作成する](#create-an-azure-ad-test-user)** -Azure AD でテスト ユーザーを作成します。
1. **[Azure AD のテスト ユーザーを割り当てる](#assign-the-azure-ad-test-user)** - テスト ユーザーが Azure 側でシングル サインオンを使用できるようにします。
1. **[Jira でテスト ユーザーを作成する](#create-the-test-user-also-in-jira)** - Jira で Azure AD テスト ユーザーに対応するテスト ユーザーを作成します。
1. **[シングル サインオンをテストする](#test-single-sign-on)** - 構成が機能するかどうかを確認します。

### <a name="configure-the-azure-ad-enterprise-application-for-single-sign-on"></a>シングル サインオン用に Azure AD エンタープライズ アプリケーションを構成する

このセクションでは、Azure portal でシングル サインオンを設定します。

SAML SSO for Jira by resolution GmbH でシングル サインオンを構成するには、次の手順のようにします。

1. [Azure portal](https://portal.azure.com/) で、作成したばかりの **SAML SSO for Jira by resolution GmbH** エンタープライズ アプリケーションの左側のパネルで **[シングル サインオン]** を選択します。

    ![シングル サインオン構成のリンク](common/select-sso.png)

2. **[シングル サインオン方式の選択]** で、 **[SAML]** モードを選択してシングル サインオンを有効にします。

    ![シングル サインオン選択モード](common/select-saml-option.png)

3. その後、 **[編集]** アイコンをクリックして、 **[基本的な SAML 構成]** ダイアログを開きます。

    ![基本的な SAML 構成を編集する](common/edit-urls.png)

4. **[基本的な SAML 構成]** セクションで、アプリケーションを **IDP** 開始モードで構成する場合は、次の手順のようにします。

    ![[識別子] と [応答 URL] が強調表示され、[保存] ボタンが選択されている [基本的な SAML 構成] セクションを示すスクリーンショット。](common/idp-intiated.png)

    a. **[識別子]** ボックスに、`https://<server-base-url>/plugins/servlet/samlsso` の形式で URL を入力します。

    b. **[応答 URL]** ボックスに、`https://<server-base-url>/plugins/servlet/samlsso` のパターンを使用して URL を入力します

    c. アプリケーションを **SP** 開始モードで構成する場合は、 **[追加の URL を設定します]** をクリックして、次の手順のようにします。

    ![[SAML SSO for Jira by resolution GmbH のドメインと URL] のシングル サインオン情報](common/metadata-upload-additional-signon.png)

    **[サインオン URL]** ボックスに、`https://<server-base-url>/plugins/servlet/samlsso` という形式で URL を入力します。

    > [!NOTE]
    > 識別子、応答 URL、サインオン URL では、 **\<server-base-url>** を Jira インスタンスのベース URL に置き換えます。 Azure portal の **[基本的な SAML 構成]** セクションに示されているパターンを参照することもできます。 問題がある場合は、[SAML SSO for Jira by resolution GmbH クライアント サポート チーム](https://www.resolution.de/go/support)に問い合わせてください。

4. **[SAML でシングル サインオンをセットアップします]** ページの **[SAML 署名証明書]** セクションで、 **フェデレーション メタデータ XML** をダウンロードし、コンピューターに保存します。

    ![証明書のダウンロードのリンク](common/metadataxml.png)

### <a name="configure-the-saml-sso-plugin-of-your-jira-instance"></a>Jira インスタンスの SAML SSO プラグインを構成する 

1. 別の Web ブラウザー ウィンドウで、Jira インスタンスに管理者としてサインインします。

2. 右側にある歯車アイコンをポイントし、 **[Manage apps]\(アプリの管理\)** をクリックします。
    
    !["歯車" アイコンを指している矢印と、ドロップダウンから選択された [Manage apps]\(アプリの管理\) を示すスクリーンショット。](./media/samlssojira-tutorial/addon1.png)

3. [Administrator Access]\(管理者アクセス\) ページにリダイレクトされる場合は、 **[Password]\(パスワード\)** を入力し、 **[Confirm]\(確認\)** ボタンをクリックします。

    ![[Administrator Access]\(管理者アクセス\) ページを示すスクリーンショット。](./media/samlssojira-tutorial/addon2.png)

4. Jira では通常、Atlassian マーケットプレースにリダイレクトされます。 そうでない場合は、左側のパネルで **[Find new apps]\(新しいアプリの検索\)** をクリックします。 **[SAML Single Sign On (SSO) for JIRA]\(JIRA の SAML シングル サインオン \(SSO\)\)** を検索し、 **[Install]\(インストール\)** ボタンをクリックして、SAML プラグインをインストールします。

    ![[Atlassian Marketplace for JIRA]\(JIRA の Atlassian マーケットプレース\) を示すスクリーンショット。[S A M L Single Sign On (S S O) Jira, S A M L/S S O]\(S A M L シングル サインオン (S S O) Jira、S A M L/S S O\) アプリの [Install]\(インストール\) ボタンを指している矢印が表示されています。](./media/samlssojira-tutorial/store.png)

5. プラグインのインストールが開始されます。 終わったら、 **[Close]\(閉じる\)** ボタンをクリックします。

    ![[Installing]\(インストール中\) ダイアログを示すスクリーンショット。](./media/samlssojira-tutorial/store-2.png)

    !["Installed and ready to go!"\(インストールされ、使用できるようになりました\) と示すスクリーンショット。 [Close]\(閉じる\) ボタンが選択されているダイアログ。](./media/samlssojira-tutorial/store-3.png)

6. 次に、 **[Manage]\(管理\)** をクリックします。

    ![[S A M L Single Sign On (S S O) Jira, S A M L/S S O]\(S A M L シングル サインオン (S S O) Jira、S A M L/S S O\) アプリを示すスクリーンショット。[Manage]\(管理\) ボタンが選択されています。](./media/samlssojira-tutorial/store-4.png)
    
8. その後、 **[Configure]\(構成\)** をクリックして、インストールしたばかりのプラグインを構成します。

    ![[Manage apps]\(アプリの管理\) ページを示すスクリーンショット。[S A M L SingleSignOn for Jira]\(Jira の S A M L シングル サインオン\) アプリの [Configure]\(構成\) ボタンが選択されています。](./media/samlssojira-tutorial/store-5.png)

9. **[SAML SingleSignOn Plugin Configuration]\(SAML SingleSignOn プラグインの構成\)** ウィザードで **[Add new IdP]\(新しい IDP の追加\)** をクリックし、新しい ID プロバイダーとして Azure AD を構成します。

    ![[Welcome]\(ようこそ\) ページを示すスクリーンショット。[Add new I d P]\(新しい I D P の追加\) ボタンが選択されています。](./media/samlssojira-tutorial/addon4.png) 

10. **[Choose your SAML Identity Provider]\(SAML ID プロバイダーの選択\)** ページで、次の手順のようにします。

    ![[Choose your S A M L Identity Provider]\(S A M L I D プロバイダーの選択\) ページを示すスクリーンショット。[I d P Type]\(I d P の種類\) および [Name]\(名前\) テキスト ボックスが強調表示され、[Next]\(次へ\) ボタンが選択されています。](./media/samlssojira-tutorial/addon5a.png)
 
    a. IDP の種類として **[Azure AD]** を設定します。
    
    b. ID プロバイダーの **[Name]\(名前\)** を追加します (例: Azure AD)。
    
    c. (省略可能) ID プロバイダーの **[Description]\(説明\)** を追加します (例: Azure AD)。
    
    d. **[次へ]** をクリックします。
    
11. **[Identity provider configuration]\(ID プロバイダーの構成\)** ページで、 **[次へ]** をクリックします。
 
    ![[Identity provider configuration]\(I D プロバイダーの構成\) ページを示すスクリーンショット。](./media/samlssojira-tutorial/addon5b.png)

12. **[Import SAML IdP Metadata]\(SAML IDP メタデータのインポート\)** ページで、次の手順を実行します。

    ![[Import S A M L I d P Metadata]\(S A M L I D P メタデータのインポート\) ページを示すスクリーンショット。[Select Metadata X M L File]\(メタデータ X M L ファイルの選択\) アクションが選択されています。](./media/samlssojira-tutorial/addon5c.png)

    a. **[Select Metadata XML File]\(メタデータ XML ファイルの選択\)** ボタンをクリックし、前にダウンロードした **フェデレーション メタデータ XML** ファイルを選択します。

    b. **[Import]\(インポート\)** ボタンをクリックします。
     
    c. インポートが成功するまでしばらく待ちます。  
     
    d. **[次へ]** をクリックします。
    
13. **[User ID attribute and transformation]\(ユーザーの ID 属性と変換\)** ページで、 **[Next]\(次へ\)** ボタンをクリックします。

    ![[User I D attribute and transformation]\(ユーザーの I D 属性と変換\) ページを示すスクリーンショット。[Next]\(次へ\) ボタンが選択されています。](./media/samlssojira-tutorial/addon5d.png)
    
14. **[User creation and update]\(ユーザーの作成と更新\)** ページで、 **[Save & Next]\(保存して次へ\)** をクリックして設定を保存します。
    
    ![[User creation and update]\(ユーザーの作成と更新\) ページを示すスクリーンショット。[Next]\(次へ\) ボタンが選択されています。](./media/samlssojira-tutorial/addon6a.png)
    
15. **[Test your settings]\(設定のテスト\)** ページで、 **[Skip test & configure manually]\(テストをスキップして手動で構成\)** をクリックして、今はユーザー テストをスキップします。 テストは次のセクションで実行し、Azure portal でいくつか設定する必要があります。
    
    ![[Test your settings]\(設定のテスト\) ページを示すスクリーンショット。[Skip test & configure manually]\(テストをスキップして手動で構成\) ボタンが選択されています。](./media/samlssojira-tutorial/addon6b.png)
    
16. **[OK]** をクリックして警告をスキップします。
    
    ![[O K] ボタンが選択されている警告ダイアログを示すスクリーンショット。](./media/samlssojira-tutorial/addon6c.png)

### <a name="create-an-azure-ad-test-user"></a>Azure AD のテスト ユーザーの作成

このセクションの目的は、Azure Portal で Britta Simon というテスト ユーザーを作成することです。 そのユーザーで、シングル サインオンをテストします。

1. Azure portal の左側のウィンドウで、 **[Azure Active Directory]** 、 **[ユーザー]** 、 **[すべてのユーザー]** の順に選択します。

    ![[ユーザーとグループ] と [すべてのユーザー] リンク](common/users.png)

2. 画面の上部にある **[新しいユーザー]** を選択します。

    ![[新しいユーザー] ボタン](common/new-user.png)

3. **[ユーザーのプロパティ]** で、次の手順のようにします。

    ![[ユーザー] ダイアログ ボックス](common/user-properties.png)

    a. **[名前]** フィールドに「 **Britta Simon** 」と入力します。
  
    b. **[ユーザー名]** フィールドに「 <b>BrittaSimon@contoso.com</b>」と入力します。

    c. **[パスワードを表示]** チェック ボックスをオンにし、[パスワード] ボックスに表示された値を書き留めます。

    d. **Create** をクリックしてください。

### <a name="assign-the-azure-ad-test-user"></a>Azure AD テスト ユーザーの割り当て

このセクションでは、Britta Simon をエンタープライズ アプリケーションに追加します。そうすると、シングル サインオンを使用できるようになります。

1. Azure portal で **[エンタープライズ アプリケーション]** を選択し、 **[すべてのアプリケーション]** を選択します。 

    ![[エンタープライズ アプリケーション] ブレード](common/enterprise-applications.png)

2. アプリケーションの一覧で、このチュートリアルの冒頭で作成したエンタープライズ アプリケーションを検索します。 チュートリアルの手順どおりに行っている場合は、 **SAML SSO for Jira by resolution GmbH** という名前です。 別の名前を指定した場合は、その名前を検索します。

    ![アプリケーションの一覧の SAML SSO for Jira by resolution GmbH のリンク](common/all-applications.png)

3. 左側で **[ユーザーとグループ]** をクリックします。

    ![[ユーザーとグループ] リンク](common/users-groups-blade.png)

4. **[ユーザーの追加]** を選択し、 **[割り当ての追加]** ダイアログで **[ユーザーとグループ]** を選択します。

    ![[割り当ての追加] ウィンドウ](common/add-assign-user.png)

5. **[ユーザーとグループ]** ダイアログの [ユーザー] の一覧から **Britta Simon** を選択し、画面の下部にある **[選択]** ボタンをクリックします。

6. SAML アサーション内に任意のロール値が必要な場合は、 **[ロールの選択]** ダイアログでユーザーに適したロールを一覧から選択し、画面の下部にある **[選択]** をクリックします。

7. **[割り当ての追加]** ダイアログで、 **[割り当て]** をクリックします。

### <a name="create-the-test-user-also-in-jira"></a>Jira でもテスト ユーザーを作成する

Azure AD ユーザーが SAML SSO for Jira by resolution GmbH にサインインできるようにするには、ユーザーを SAML SSO for Jira by resolution GmbH にプロビジョニングする必要があります。 このチュートリアルの場合、プロビジョニングは手作業で行う必要があります。 ただし、resolution による SAML SSO プラグインでは、他のプロビジョニング モデルも使用できます ( **Just In Time** プロビジョニングなど)。 [SAML SSO by resolution GmbH](https://wiki.resolution.de/doc/saml-sso/latest/all) のドキュメントをご覧ください。 質問がある場合は、[resolution のサポート](https://www.resolution.de/go/support)に問い合わせてください。

**ユーザー アカウントを手作業でプロビジョニングするには、次の手順のようにします。**

1. 管理者として Jira インスタンスにサインインします。

2. 歯車アイコンをポイントし、 **[User management]\(ユーザー管理\)** を選択します。

   !["歯車" アイコンを指している矢印と、ドロップダウンから選択された [User management]\(ユーザー管理\) を示すスクリーンショット。](./media/samlssojira-tutorial/user1.png)

3. [Administrator Access]\(管理者アクセス\) ページにリダイレクトされる場合は、 **[Password]\(パスワード\)** を入力し、 **[Confirm]\(確認\)** ボタンをクリックします。

    ![[Administrator Access]\(管理者アクセス\) ページを示すスクリーンショット。[Password]\(パスワード\) テキスト ボックスが強調表示されています。](./media/samlssojira-tutorial/user2.png) 

4. **[User management]\(ユーザー管理\)** タブ セクションで、 **[create user]\(ユーザーの作成\)** をクリックします。

    ![[User management]\(ユーザー管理\) タブを示すスクリーンショット。[Create user]\(ユーザーの作成\) ボタンが選択されています。](./media/samlssojira-tutorial/user3-new.png) 

5. **[Create new user]\(新しいユーザーの作成\)** ダイアログ ページで、次の手順のようにします。 Azure AD とまったく同じようにユーザーを作成する必要があります。

    ![従業員の追加](./media/samlssojira-tutorial/user4-new.png) 

    a. **[Email address]\(電子メール アドレス\)** ボックスに、ユーザーのメール アドレス <b>BrittaSimon@contoso.com</b> を入力します。

    b. **[Full Name]\(フル ネーム\)** ボックスに、ユーザーの氏名を入力します: **Britta Simon** 。

    c. **[Username]\(ユーザー名\)** ボックスに、ユーザーのメール アドレス <b>BrittaSimon@contoso.com</b> を入力します。 

    d. **[Password]\(パスワード\)** ボックスに、ユーザーのパスワードを入力します。

    e. **[Create user]\(ユーザーの作成\)** をクリックして、ユーザーの作成を完了します。

### <a name="test-single-sign-on"></a>シングル サインオンのテスト

このセクションでは、アクセス パネルを使用して Azure AD のシングル サインオン構成をテストします。

アクセス パネルで [SAML SSO for Jira by resolution GmbH] タイルをクリックすると、SSO を設定した SAML SSO for Jira by resolution GmbH に自動的にサインインします。 アクセス パネルの詳細については、[アクセス パネルの概要](../user-help/my-apps-portal-end-user-access.md)に関する記事を参照してください。

`https://<server-base-url>/plugins/servlet/samlsso` に移動すると、シングル サインオンをテストすることもできます。 **\<server-base-url>** は、Jira インスタンスのベース URL に置き換えます。


## <a name="enable-single-sign-on-redirection-for-jira"></a>Jira のシングル サインオン リダイレクトを有効にする

前のセクションで説明したように、現在、シングル サインオンをトリガーするには 2 つの方法があります。 **Azure portal** を使用するか、または **Jira インスタンスへの特別なリンク** を使用します。 resolution GmbH による SAML SSO プラグインでは、単純に **Jira インスタンスを指している任意の URL にアクセスする** ことでシングル サインオンをトリガーすることもできます。

基本的に、Jira にアクセスするすべてのユーザーは、プラグインでオプションをアクティブ化した後、シングル サインオンにリダイレクトされます。

SSO リダイレクトを有効にするには、 **お使いの Jira インスタンス** で次のようにします。

1. Jira で SAML SSO プラグインの構成ページにアクセスします。
1. 左側のパネルで **[Redirection]\(リダイレクト\)** をクリックします。

   ![Jira の SAML SingleSignOn プラグインの構成ページの断片的なスクリーンショット (左側のナビゲーションにある [Redirection]\(リダイレクト\) リンクを強調表示したところ)。](./media/samlssojira-tutorial/ssore1.png)

1. **[Enable SSO Redirect]\(SSO リダイレクトを有効にする\)** をオンにします。

   ![Jira の SAML SingleSignOn プラグインの構成ページの断片的なスクリーンショット ([Enable SSO Redirect]\(SSO リダイレクトを有効にする\) チェック ボックスのオン状態を強調表示したところ)。](./media/samlssojira-tutorial/ssore2.png) 

1. 右上隅の **[Save Settings]\(設定の保存\)** ボタンをクリックします。

`https://\<server-base-url>/login.jsp?nosso` に移動して **[Enable nosso]\(nosso を有効にする\)** をオンにした場合は、このオプションを有効にした後でもユーザー名とパスワードの入力を求められることがあります。 やはり、 **\<server-base-url>** はベース URL に置き換えます。


## <a name="additional-resources"></a>その他のリソース

- [SaaS アプリと Azure Active Directory を統合する方法に関するチュートリアルの一覧](./tutorial-list.md)

- [Azure Active Directory のアプリケーション アクセスとシングル サインオンとは](../manage-apps/what-is-single-sign-on.md)

- [Azure Active Directory の条件付きアクセスとは](../conditional-access/overview.md)