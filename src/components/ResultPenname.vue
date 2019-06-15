<template>

    <div class="result">
        <p>あなたの芸名・ペンネームは</p>
        <p class="penname">{{penName}}</p>
        <p>得意ネタ：</p>
        <p class="gag">{{gag}}</p>
        <div class="pose">
            <p class="say">いいかた</p>
            <div class="balloon"> {{gag}}</div>
            <img :src="pose">
        </div>
        <button @click="choiceNumber">別の名前にする</button>
    </div>
</template>
<script>
    export default {
        props: {
            inputData: {
                name: String,
                sex: Number,
            },
        },
        data() {
            return {
                choicePennameIndex: 0,
                choiceGagIndex: 0,
                choicePoseIndex: 0,
            }
        },
        created() {
            this.choicePennameIndex = Math.floor(Math.random() * Math.floor(this.penNameList.length));
            this.choiceGagIndex = Math.floor(Math.random() * Math.floor(this.gagList.length));
            this.choicePoseIndex = Math.floor(Math.random() * Math.floor(this.poseList.length));
        },
        methods: {
            choiceNumber: function () {
                this.choicePennameIndex = Math.floor(Math.random() * Math.floor(this.penNameList.length));
                this.choiceGagIndex = Math.floor(Math.random() * Math.floor(this.gagList.length));
                this.choicePoseIndex = Math.floor(Math.random() * Math.floor(this.poseList.length));
            }
        },
        computed: {
            penNameList() {
                if (this.inputData.sex == 1) {
                    return ["ペニンシュラ" + this.inputData.name,
                        "ナポリタン" + this.inputData.name,
                        this.inputData.name + "地獄",
                        this.inputData.name + "ポン吉",
                        "ダルビッ" + this.inputData.name,
                        "ポップコーン" + this.inputData.name,
                        "運転手は" + this.inputData.name,
                        "メゾン" + this.inputData.name,
                        "誰なんだ" + this.inputData.name,
                        this.inputData.name + "ベトコン",
                        "チッチョリーナ" + this.inputData.name,
                        "ガム" + this.inputData.name,
                        this.inputData.name + "きんにくん",
                        "Tボーン" + this.inputData.name,
                        this.inputData.name + "南蛮渡来",
                        "ゆで時間" + this.inputData.name,
                        "炭カル袋" + this.inputData.name,
                        "生センマイ" + this.inputData.name,
                        "夕陽が丘の" + this.inputData.name + "大臣",
                        "ケンタッキーフライド" + this.inputData.name,
                        "縄文式" + this.inputData.name,
                        "墾田永年私財" + this.inputData.name,
                        "ヒゲ" + this.inputData.name,
                        this.inputData.name + "幕府",
                        "ロマンスカー" + this.inputData.name,
                        "パンタロン" + this.inputData.name,
                        "ぶっちぎりマイ" + this.inputData.name,
                        this.inputData.name + "コールタール",
                        "メロンパンナちゃん（" + this.inputData.name + "）",
                        this.inputData.name + "馬",
                        "ヒューレット・パッカー" + this.inputData.name,
                        this.inputData.name + "ウオーズ",
                        "もしも" + this.inputData.name + "が弾けたなら",
                        this.inputData.name + "軍団",
                        "アリトキリギリ" + this.inputData.name,
                        this.inputData.name + "県警",
                        this.inputData.name + " with 枕木",
                        "歯形がついてるほうの" + this.inputData.name,
                        this.inputData.name + "メタリカ",
                        this.inputData.name + "ゼリー状",
                        this.inputData.name + "ベータ版",
                        this.inputData.name + "シリカゲル",
                        this.inputData.name + "諸島",
                        this.inputData.name + "式海岸",
                        "ホテル" + this.inputData.name,
                        this.inputData.name + "マン",
                        this.inputData.name + "フラワーロック",
                        this.inputData.name + "副部長",
                        this.inputData.name + "ライダー",
                        "レバニラ" + this.inputData.name,
                    ];
                } else {
                    return ["マドモワゼル" + this.inputData.name,
                        this.inputData.name + "ポン子",
                        this.inputData.name + "の館",
                        "クリスチーヌ" + this.inputData.name,
                        "ピンク色大好き" + this.inputData.name,
                        this.inputData.name + "パー子",
                        this.inputData.name + "ヘビ子",
                        this.inputData.name + "デンキ子",
                        "フランソワーヌ" + this.inputData.name,
                        "ギョラン坂" + this.inputData.name,
                        this.inputData.name + "ウニ子",
                        this.inputData.name + "・バル・タン子",
                        this.inputData.name + "=ザビ・エル子",
                        this.inputData.name + "=レバカツ子",
                        "パウダー" + this.inputData.name,
                        "レーニン" + this.inputData.name,
                        this.inputData.name + "夫人",
                        "シベリアン" + this.inputData.name,
                        this.inputData.name + "シベリア",
                        this.inputData.name + "ビンタ",
                        this.inputData.name + "パスファインダー",
                        "クリーミー" + this.inputData.name,
                        this.inputData.name + "細胞",
                        this.inputData.name + "13世",
                        this.inputData.name + "ペタバイト",
                        this.inputData.name + "炒め",
                        this.inputData.name + "待合室",
                        "リニア" + this.inputData.name,
                        this.inputData.name + "準備室",
                        "ワンピース" + this.inputData.name,
                        "フリル" + this.inputData.name,
                        this.inputData.name + "ッティア",
                        this.inputData.name + "ティー",
                        this.inputData.name + "プラザ",
                        this.inputData.name + "海溝",
                        "マウンテン" + this.inputData.name,
                        "ダイナミック" + this.inputData.name,
                        "花ことばは" + this.inputData.name,
                        "すし花館" + this.inputData.name,
                        "ラスト" + this.inputData.name + "ンペラー",
                        "夢の" + this.inputData.name,
                        this.inputData.name + "出世払い",
                        "USB" + this.inputData.name,
                        "アルカリイオン" + this.inputData.name,
                        "カルーセル" + this.inputData.name,
                        "カテーテル" + this.inputData.name,
                        "科学忍者" + this.inputData.name,
                        "マッド" + this.inputData.name,
                        "ゴールデンハンマー" + this.inputData.name,
                        this.inputData.name + "は底なし沼",
                        "スナック" + this.inputData.name,
                    ];
                }
            },
            gagList() {
                if (this.inputData.sex == 1) {
                    return ["干し首にするぞ！",
                        "スカンジナビア！",
                        "それ、甘いの？",
                        "100円ってところかな",
                        "これ、あげる",
                        "ペンディング！",
                        "アポイントメンツ",
                        "踏まないで",
                        "クマが来たぞ",
                        "ヘビが来るぞ",
                        "実は猫でした",
                        "ぬるぬるするけどね",
                        "どうせベニヤだろ",
                        "ニャッツシアター",
                        "ヘイ！ミルクピッチャー！",
                        "は−、スジャータスジャータ",
                        "毛、はえた？",
                        "いただきマンモグラフィー",
                        "ウニのにおいがする",
                        "考え中です",
                        "鼻パックかよ",
                        "きみ、いい腎臓してるなー",
                        "赤くなるのです",
                        "アルゼンチン！",
                        "メカニカル〜",
                        "トロピカル〜",
                        "はい！寝てました",
                        "バリウム飲ますぞ！",
                        "晩ごはんは胃カメラ",
                        "私の赤ちゃん！あ、コロッケか",
                        "リモコンはどこ？",
                        "どこのダイソー？",
                        "羽化するとこだった",
                        "ラーメンで言うと五杯分",
                        "うんこじゃん！",
                        "水晶玉がそう言ってる",
                        "ちょっとくさいぞ",
                        "エクトプラズム２割増量",
                        "ホラー映画で２分で死ぬタイプ",
                        "ミシッ！メシッ！",
                        "そうでチュー",
                        "ジャブジャブ！シャブ！",
                        "チャーハンタイム",
                        "チョモランマ！",
                        "おれの鼻息を受けてみろ",
                        "全身FILA",
                        "テニス五段",
                        "ティッシュペーパー大好き！",
                        "そう来たか",
                        "ノーサンキュー",
                    ];
                } else {
                    return ["水たまりでじゅうぶんよ",
                        "あたしのは養分があるわよ",
                        "ごめんあそばせ子！",
                        "言ったとか、言わないとか",
                        "パンの耳！",
                        "マルチーズでも知ってるわ",
                        "煮こむわよ",
                        "中身はつかうわよ",
                        "フランチビーム",
                        "バーキンの足袋",
                        "とんだハマトラよ",
                        "ユニクロ？いや、西友",
                        "もーい",
                        "だから言ってやったのよ",
                        "うちはベータだから",
                        "ベッドでもオフサイドよ",
                        "持って帰りなさいよー",
                        "大将、やってる？",
                        "もうひと声！",
                        "もうべったべた",
                        "ウイーッス",
                        "あーよく寝た",
                        "スキップで移動します",
                        "あーテンションプリーズ",
                        "前方ヨーシ",
                        "ユーモラスねー",
                        "とんちをきかせなさい",
                        "仕入はどこで？",
                        "それは違います",
                        "ブログに書かなきゃ",
                        "全部うそだけど",
                        "樹齢100年",
                        "コンプライアンス！",
                        "二級河川！",
                        "目が飛び出たわよ",
                        "悪いごはいねえがー",
                        "もちろん半身浴",
                        "どうせCGでしょ",
                        "キャタピラなぎさ",
                        "なめんなよ",
                        "さわるなよ",
                        "ヘモグロビーン！",
                        "プラナリアー",
                        "ドビュッシー！",
                        "これはあかん",
                        "それは、ヒ・ミ・ツ",
                        "アヒャパー",
                        "グロッキーグロッキー",
                        "アフロぼーん",
                        "あら、うんこみたいだわ",
                    ];
                }
            },
            poseList() {
                if (this.inputData.sex == 1) {
                    return [
                        require("@/assets/img/01_01.gif"),
                        require("@/assets/img/01_02.gif"),
                        require("@/assets/img/01_03.gif"),
                        require("@/assets/img/01_04.gif"),
                        require("@/assets/img/01_05.gif"),
                        require("@/assets/img/01_06.gif"),
                        require("@/assets/img/01_07.gif"),
                        require("@/assets/img/01_08.gif"),
                        require("@/assets/img/01_09.gif"),
                        require("@/assets/img/01_11.gif"),
                        require("@/assets/img/01_12.gif"),
                        require("@/assets/img/01_13.gif"),
                        require("@/assets/img/01_14.gif"),
                        require("@/assets/img/01_15.gif"),
                        require("@/assets/img/01_16.gif"),
                        require("@/assets/img/01_17.gif"),
                        require("@/assets/img/01_18.gif"),
                        require("@/assets/img/01_19.gif"),];
                } else {
                    return [
                        require("@/assets/img/02_01.gif"),
                        require("@/assets/img/02_02.gif"),
                        require("@/assets/img/02_03.gif"),
                        require("@/assets/img/02_04.gif"),
                        require("@/assets/img/02_05.gif"),
                        require("@/assets/img/02_06.gif"),
                        require("@/assets/img/02_07.gif"),
                        require("@/assets/img/02_08.gif"),
                        require("@/assets/img/02_09.gif"),
                        require("@/assets/img/02_11.gif"),
                        require("@/assets/img/02_12.gif"),
                        require("@/assets/img/02_13.gif"),
                        require("@/assets/img/02_14.gif"),
                        require("@/assets/img/02_15.gif"),
                        require("@/assets/img/02_16.gif"),
                        require("@/assets/img/02_17.gif"),
                        require("@/assets/img/02_18.gif"),
                        require("@/assets/img/02_19.gif"),
                        require("@/assets/img/02_20.gif"),
                    ];
                }
            },
            penName() {
                return this.penNameList[this.choicePennameIndex];
            },
            gag() {
                return this.gagList[this.choiceGagIndex];
            },
            pose() {
                return this.poseList[this.choicePoseIndex];
            },

        }
    }
</script>
<style scoped>
    p {
        font-size: 12px;
        line-height: 148%;
    }

    .penname, .gag {
        font-size: 40px;
        font-family: "メイリオ", "ＭＳ Ｐゴシック", Osaka, "ヒラギノ角ゴ Pro W3";
        font-weight: bolder;
        margin-top: 5px;
    }

    .result {
        width: 500px;
        border-radius: 2px;
        border: solid 2px #000;
        text-align: left;
        padding: 10px;
    }

    .say {
        text-align: left;
    }

    .balloon {
        position: relative;
        margin-bottom: 20px;
        padding: 10px 30px;
        border: 2px solid #000;
        border-radius: 10px;
        text-align: left;
        letter-spacing: .11em;
        width: 320px;
        font-size: medium;
        font-family: "メイリオ", "ＭＳ Ｐゴシック", Osaka, "ヒラギノ角ゴ Pro W3";
    }

    .balloon:after {
        position: absolute;
        left: calc(50% - 10px);
        bottom: -13px;
        content: "";
        width: 20px;
        height: 20px;
        border-top: solid 2px #000;
        border-right: solid 2px #000;
        -ms-transform: rotate(135deg);
        -webkit-transform: rotate(135deg);
        transform: rotate(135deg);
        background-color: #fff;
    }

    .pose {
        text-align: center;
        margin-left: 40px;
        width: 400px;
    }

    button {
        -webkit-appearance: push-button;
        user-select: none;
        white-space: pre;

    }
</style>
