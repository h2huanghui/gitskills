
## 描述


## 版本历史
CBOSS_LV_2017.14


## 用例
测试点|预期结果
:---:|:---
搜索|invoice状态：多项搜索<br>费用名称：模糊搜索，搜出包含搜索费用的invoice。费用定义的名称搜索<br>结清时间：时间范围搜索
显示项|invoice date：精确到时分秒显示<br>到账金额：应付款之后<br>到账金额=invoice的grand total金额-关联充值记录的手续费之和

## 列表SQL
```
select cci.invoice_no       Invoice编号,
       cci.billing_com_name Invoice公司名称,
       cci.create_time      InvoiceDate,
       cci.status           invoice状态,
       cci.grand_amount      应付款,
       cci.PAY_AMOUNT_CNY    优惠后总额人民币,
       cci.pay_amount_usd    优惠后总额美元
  from cb.cb_cost_invoice cci
 where cci.mic_com_id = 11
 order by cci.create_time DESC
```


## 参考需求


## 参考用例


## 其它

