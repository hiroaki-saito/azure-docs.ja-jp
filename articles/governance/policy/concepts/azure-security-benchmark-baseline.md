---
title: Azure セキュリティ ベンチマーク用の Azure Policy セキュリティ ベースライン
description: Azure Policy セキュリティ ベースラインでは、Azure セキュリティ ベンチマークで指定されているセキュリティに関する推奨事項を実装するための手順のガイダンスとリソースが提供されます。
author: msmbaldwin
ms.service: azure-policy
ms.topic: conceptual
ms.date: 07/02/2020
ms.author: mbaldwin
ms.custom: subject-security-benchmark
ms.openlocfilehash: e8915e1c15972341befd176b412925f4e87c94f6
ms.sourcegitcommit: 2bd0a039be8126c969a795cea3b60ce8e4ce64fc
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/14/2021
ms.locfileid: "98201452"
---
# <a name="azure-policy-security-baseline-for-azure-security-benchmark"></a>Azure セキュリティ ベンチマーク用の Azure Policy セキュリティ ベースライン

このセキュリティ ベースラインは、[Azure セキュリティ ベンチマーク](../../../security/benchmarks/overview.md)のガイダンスを Azure Policy に適用します。 Azure セキュリティ ベンチマークには、Azure 上のクラウド ソリューションをセキュリティで保護する方法に関する推奨事項がまとめてあります。 内容は、**コンプライアンス ドメイン** および **セキュリティ制御** によってグループ化されています。これらは、Azure セキュリティ ベンチマークと、Azure Policy に適用できる関連ガイダンスによって定義されています。 Azure Policy に適用できない **制御** は、除外されています。 Azure Policy を完全に Azure セキュリティ ベンチマークにマップする方法については、[完全な Azure Policy セキュリティ ベースライン マッピング ファイル](https://github.com/MicrosoftDocs/SecurityBenchmarks/tree/master/Azure%20Offer%20Security%20Baselines)を参照してください。

組み込みイニシアチブによって Azure セキュリティ ベンチマーク制御を組み込みのポリシー定義にマッピングする方法については、[規制コンプライアンスの Azure セキュリティ ベンチマーク](../samples/azure-security-benchmark.md)に関するページを参照してください。

Azure Policy では、"_責任_" の代わりに "_所有権_" という用語を使用します。 "_所有権_" の詳細については、[Azure Policy のポリシー定義](./definition-structure.md#type)に関するセクションと、「[クラウドにおける共同責任](../../../security/fundamentals/shared-responsibility.md)」を参照してください。


## <a name="logging-and-monitoring"></a>ログ記録と監視

*詳細については、「[セキュリティ コントロール: ログ記録と監視](../../../security/benchmarks/security-control-logging-monitoring.md)」を参照してください。*

### <a name="23-enable-audit-logging-for-azure-resources"></a>2.3:Azure リソースの監査ログ記録を有効にする

**ガイダンス**:Azure Policy では、アクティビティ ログ (自動的に有効になります) を使用して、イベント ソース、日付、ユーザー、タイムスタンプ、送信元アドレス、送信先アドレス、その他の役立つ要素が記録されます。

* [Azure Monitor でプラットフォーム ログとメトリックを収集する方法](../../../azure-monitor/platform/diagnostic-settings.md)

* [Azure でのログ記録とログのさまざまな種類について](../../../azure-monitor/platform/platform-logs-overview.md)


**Azure Security Center の監視**: 現在は使用できません

**責任**: Customer

## <a name="identity-and-access-control"></a>ID とアクセスの制御

*詳細については、「[セキュリティ コントロール: ID およびアクセス制御](../../../security/benchmarks/security-control-identity-access-control.md)」を参照してください。*

### <a name="33-use-dedicated-administrative-accounts"></a>3.3: 専用管理者アカウントを使用する

**ガイダンス**: 専用管理者アカウントの使用に関する標準的な操作手順を作成します。 Azure Security Center ID とアクセス管理を使用して、管理者アカウントの数を監視します。 

また、[Azure AD Privileged Identity Management](../../../active-directory/privileged-identity-management/pim-configure.md) の特権ロールまたは [Azure Resource Manager](../../../azure-resource-manager/management/overview.md) を使用して、Just-In-Time または Just-Enough-Access を有効にすることもできます。


**Azure Security Center の監視**: 現在は使用できません

**責任**: Customer

### <a name="36-use-dedicated-machines-privileged-access-workstations-for-all-administrative-tasks"></a>3.6: すべての管理タスクに専用マシン (特権アクセス ワークステーション) を使用する

**ガイダンス**: MFA が構成されている PAW (特権アクセス ワークステーション) を使用して Azure リソースにログインし、構成します。

* [特権アクセス ワークステーションについて](https://4sysops.com/archives/understand-the-microsoft-privileged-access-workstation-paw-security-model/)

* [Azure で MFA を有効にする方法](../../../active-directory/authentication/howto-mfa-getstarted.md)


**Azure Security Center の監視**: 適用なし

**責任**: Customer

## <a name="data-protection"></a>データ保護

*詳細については、「[セキュリティ コントロール: データ保護](../../../security/benchmarks/security-control-data-protection.md)」を参照してください。*

### <a name="46-use-azure-rbac-to-control-access-to-resources"></a>4.6:Azure RBAC を使用してリソースへのアクセスを制御する

**ガイダンス**: Azure ロールベースのアクセス制御 (Azure RBAC) を使用して、Azure Policy へのアクセスを制御します。

* [Azure Policy における Azure RBAC アクセス許可](../overview.md#azure-rbac-permissions-in-azure-policy)

* [Azure RBAC を構成する方法](../../../role-based-access-control/role-assignments-portal.md)


**Azure Security Center の監視**: 現在は使用できません

**責任**: Customer

### <a name="49-log-and-alert-on-changes-to-critical-azure-resources"></a>4.9:重要な Azure リソースへの変更に関するログとアラート

**ガイダンス**: Azure Monitor とアクティビティ ログを使用して、Azure Policy が変更された場合のアラートを作成します。

* [Azure アクティビティ ログ イベントのアラートを作成する方法](../../../azure-monitor/platform/alerts-activity-log.md)


**Azure Security Center の監視**: 現在は使用できません

**責任**: Customer

## <a name="inventory-and-asset-management"></a>インベントリと資産の管理

*詳細については、「[セキュリティ コントロール: インベントリと資産の管理](../../../security/benchmarks/security-control-inventory-asset-management.md)」を参照してください。*

### <a name="62-maintain-asset-metadata"></a>6.2:資産メタデータを保持する

**ガイダンス**:メタデータを提供する Azure リソースにタグを適用すると、それらのリソースが各分類に論理的に整理されます。 Azure Policy の "_変更_" 効果を使用して、コンプライアンスおよび一貫性のあるタグ ガバナンスについてレポートし、これらを適用します。

* [チュートリアル:ポリシーを作成および管理する](../tutorials/create-and-manage.md)

* [チュートリアル:タグ ガバナンスを管理する](../tutorials/govern-tags.md)


**Azure Security Center の監視**: 現在は使用できません

**責任**: Customer

### <a name="64-define-and-maintain-an-inventory-of-approved-azure-resources"></a>6.4:承認された Azure リソースのインベントリを定義および管理する

**ガイダンス**: 組織のニーズに応じて、承認されたポリシー定義およびポリシー割り当てのインベントリを作成します。

**Azure Security Center の監視**: 適用なし

**責任**: Customer

### <a name="65-monitor-for-unapproved-azure-resources"></a>6.5:承認されていない Azure リソースを監視する

**ガイダンス**: Azure Policy を使用して、サブスクリプションで作成できるリソースの種類に制限を設けます。

* [Azure Policy を構成して管理する方法](../tutorials/create-and-manage.md)


**Azure Security Center の監視**: 適用なし

**責任**: Customer

## <a name="next-steps"></a>次のステップ

- [Azure セキュリティ ベンチマーク](../../../security/benchmarks/overview.md)に関するページを参照する
- [Azure セキュリティ ベースライン](../../../security/benchmarks/security-baselines-overview.md)の詳細について学習する
