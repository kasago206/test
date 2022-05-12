# 追加資料

##  サンプルコード集

全角→半角の変換などは不要、このままコピペすれば動きます。

### 直リンク読み込み

```python
!wget https://raw.githubusercontent.com/kasago206/test/main/colortv.csv
!head colortv.csv
```

### マウント
- マウントする前に**必ず**「Data」フォルダをgoogle driveのルートディレクトリに作成し、中にgdp_alt.csvを置いておくこと。 フォルダが存在しない場合自動で作成してくれる機能は無いのでマウントできない。

```python
from google.colab import drive
drive.mount('/content/drive') 

#csv読み込み
import pandas as pd
file_data = pd.read_csv('drive/My Drive/Data/gdp_alt.csv')
file_data.head()
```

### データフレーム作成

```python
import numpy as np
import pandas as pd
sample_array = np.array([1,2,3,4,5])
sample_array

sample_df = pd.DataFrame({
'col1' : sample_array,
'col2' : sample_array * 2,
'col3' : ["A", "B", "C", "D", "E"]
})
print(sample_df)

#csv書き出し
sample_df . to_csv("array.csv")
```

### データフレーム結合

```python
df_1 = pd.DataFrame({

'col1' : np.array([1,2,3]),
'col2' : ["A", "B", "C"]
})
df_2 = pd.DataFrame({
'col1' : np.array([4,5,6]),
'col2' : ["D", "E", "F"]
})
print(pd.concat([df_1, df_2]))
```

### xlsxファイル読み込み

```python
df_3 = pd.read_excel('drive/My Drive/Data/data1.xlsx')
df_3.head()
```
