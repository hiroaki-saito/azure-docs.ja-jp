---
author: roygara
ms.service: virtual-machines
ms.topic: include
ms.date: 03/18/2019
ms.author: rogarana
ms.openlocfilehash: ffb07220267a2c192b4aad2405185c80bd9abbc0
ms.sourcegitcommit: 4bee52a3601b226cfc4e6eac71c1cb3b4b0eafe2
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/11/2020
ms.locfileid: "94523931"
---
Azure 仮想マシンには複数のデータ ディスクを接続できます。 VM のデータ ディスクのスケーラビリティとパフォーマンスの目標に基づいて、パフォーマンスとキャパシティの要件を満たすために必要なディスクの数と種類を決定します。

> [!IMPORTANT]
> パフォーマンスを最適化するには、仮想マシンに接続する使用率が高いディスク数を制限して、スロットルを回避するようにします。 接続されているすべてのディスクの使用率が同時に高くならなければ、仮想マシンは多数のディスクに対応できます。

**Azure Managed Disks の場合:**

次の表は、サブスクリプションあたりのリージョンごとのリソース数の既定の制限と上限を示しています。 制限は、プラットフォーム マネージド キーまたはカスタマー マネージド キーで暗号化されたディスクに関係なく変わりません。 リソース グループあたりの Managed Disks、スナップショット、イメージの数に制限はありません。  

> | リソース | 制限 |
> | --- | --- |
> | Standard マネージド ディスク | 50,000 |
> | Standard SSD マネージド ディスク | 50,000 |
> | Premium マネージド ディスク | 50,000 |
> | Standard_LRS スナップショット | 50,000 |
> | Standard_ZRS スナップショット | 50,000 |
> | マネージド イメージ | 50,000 |

**Standard ストレージ アカウントの場合:** Standard ストレージ アカウントには、20,000 IOPS という最大合計要求レートがあります。 Standard ストレージ アカウントの仮想マシン ディスク全体の合計 IOPS は、この制限を超えることはできません。
  
1 つの Standard ストレージ アカウントでサポートされる使用率が高いディスク数は、要求レート制限に基づいて概算できます。 たとえば、Basic レベルの VM では、使用率の高いディスクの最大数は約 66 (ディスクあたり 20,000/300 IOPS) です。 Standard レベルの VM では、使用率の高いディスクの最大数は約 40 (ディスクあたり IOPS 20,000/500 IOPS) です。 

**Premium ストレージ アカウントの場合:** Premium ストレージ アカウントの最大合計スループット レートは 50 Gbps です。 すべての VM ディスク全体の合計スループットは、この制限を超えることはできません。

