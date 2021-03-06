---
author: alkohli
ms.service: databox
ms.topic: include
ms.date: 10/15/2020
ms.author: alkohli
ms.openlocfilehash: 385ebffb4780543b532c81b89f1847f5c84cd0ac
ms.sourcegitcommit: 16c7fd8fe944ece07b6cf42a9c0e82b057900662
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/03/2020
ms.locfileid: "96581201"
---
Azure にデータを移動する際には、次の注意事項がデータに適用されます。

- 複数のデバイスが同じコンテナーに書き込まないようにすることをお勧めします。
- コピー対象のオブジェクトと同じ名前の既存の Azure オブジェクト (BLOB やファイルなど) がクラウド内にある場合、デバイスはクラウド内のファイルを上書きします。
- 共有フォルダーの下に作成される空のディレクトリ階層 (ファイルを含まない) は、BLOB コンテナーにアップロードされません。
- エクスプローラーでのドラッグ アンド ドロップまたはコマンド ラインを使用して、データをコピーできます。 コピーするファイルの合計サイズが 10 GB を超える場合は、`Robocopy` や `rsync` などの一括コピー プログラムを使用することをお勧めします。 一括コピー ツールを使用すると、断続的なエラーの場合にコピー操作が再試行され、回復性が向上します。
- Azure Storage コンテナーに関連付けられた共有から、作成時に共有に定義された BLOB の種類と一致しない BLOB がアップロードされた場合、そのような BLOB は更新されません。 たとえば、デバイスにブロック BLOB 共有を作成して、ページ BLOB を含む既存のクラウド コンテナーに共有を関連付け、その共有を更新してファイルをダウンロードしてから、クラウドにページ BLOB として既に格納されているいくつかの最新ファイルを変更する場合は、アップロード エラーが表示されます。
- 共有にファイルを作成した後に、ファイル名を変更することはできません。
- 共有からファイルを削除しても、ストレージ アカウントのエントリは削除されません。
- データのコピーに `rsync` を使用している場合、`rsync -a` オプションはサポートされません。