# mozc-ibus-split

[English] / [日本語]

## Overview
A custom setup to split the Mozc IBus engine into two completely independent engines: one dedicated to Hiragana and another to Full Katakana. Designed for heavy Japanese typists on Linux environments to eliminate the need for manual mode toggling.

MozcのIBusエンジンを「ひらがな」と「全角カタカナ」の2つの完全に独立したエンジンに分離するためのカスタムセットアップです。Linux環境で頻繁に日本語を入力するユーザー向けに設計されており、手動での入力モード切り替えを不要にします。

## Features / 特徴
- Independent IBus engines for Hiragana and Katakana.
- No need to use shortcut keys for switching composition modes.
- Safe installation process with automated backup of the original binaries.

- ひらがなとカタカナの独立したIBusエンジンを提供。
- 入力モード切り替えのためのショートカットキー操作が不要。
- オリジナルバイナリの自動バックアップを伴う安全なインストールプロセス。

## Requirements / 要件
- Ubuntu 24.04 LTS
- IBus framework
- Git
- curl

## Installation / インストール
Run the installation script. This script will automatically download the necessary dependencies, back up your existing `ibus-engine-mozc`, build the latest Mozc from source via Bazel, and deploy the separated configuration.

インストールスクリプトを実行してください。このスクリプトは必要な依存関係を自動的にダウンロードし、既存の `ibus-engine-mozc` をバックアップした上で、Bazel経由で最新のMozcをソースからビルドし、分離設定を適用します。

bash
git clone https://github.com/your-username/mozc-ibus-split.git
cd mozc-ibus-split/scripts
chmod +x install.sh
./install.sh


## Rollback (Recovery) / ロールバック (復元)
If you encounter any issues or wish to revert to the default single-engine Mozc, run the rollback script. It will safely restore your backed-up binary and restart the IBus daemon.

問題が発生した場合、またはデフォルトの単一エンジン版Mozcに戻したい場合は、ロールバックスクリプトを実行してください。バックアップされたバイナリを安全に復元し、IBusデーモンを再起動します。

bash
cd mozc-ibus-split/scripts
chmod +x rollback.sh
./rollback.sh


## Disclaimer / 免責事項
This project modifies user-space binaries and IBus configurations. It does not modify kernel-level operations. However, please use it at your own risk. 

本プロジェクトはユーザースペースのバイナリおよびIBus設定を変更します。カーネルレベルの操作は行いません。ただし、ご自身の責任においてご使用ください。
