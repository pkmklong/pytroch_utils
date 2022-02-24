# pytorch_utils (WIP)

<b>Installation</b>

    $ python3 -m pip install git+https://github.com/pkmklong/pytorch_utils.git
 
<i>Synthetic Data Generation</i>

```python
from pytorch.utils import MockDataset

train_dataset = MockDataset(
    features=5,
    pos_n=100,
    neg_n=100,
    pos_mean=150,
    pos_std=80,
    neg_mean=200,
    neg_std=100
)

train_dataset.data.shape
>> torch.Size([200, 5])

df = train_dataset.to_df(row_ids=True, label=True)
print(df.head(5))
>>         col_0       col_1       col_2       col_3       col_4  row_ids  label
>> 0  148.404175   26.659887  182.252655   88.354713   80.416580        0    1.0
>> 1  177.925339   49.712185  192.029495  195.813110   88.991829        1    1.0
>> 2   30.146475  207.450897  193.121506  156.405838   92.489151        2    1.0
>> 3  335.195282  222.256516  133.536621   34.579933  215.421402        3    1.0
>> 4  351.968506  375.252045  112.089806  200.617950  175.515839        4    1.0  

visualize_data(train_dataset.data, train_dataset.label, x1=1, x2=2)
plt.show()
```
<img src="https://github.com/pkmklong/pytorch_utils/blob/main/images/demo_data.png" height="400" class="center" title="Synthetic Data Plotting">

