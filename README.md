import re

match_obj = re.match(
    '<(?P<n1>[_0-9a-zA-Z]+)><(?P<n2>[_0-9a-zA-Z]+)><(?P<n3>[_0-9a-zA-Z]+)>(.*)</(?P=n3)><(?P<n4>[_0-9a-zA-Z]+)>(.*)</(?P=n4)><(?P<n5>[_0-9a-zA-Z]+)>(.*)</(?P=n5)><(?P<n6>[_0-9a-zA-Z]+)>(.*)</(?P=n6)><(?P<n7>[_0-9a-zA-Z]+)>(.*)</(?P=n7)><(?P<n8>[_0-9a-zA-Z]+)>(.*)</(?P=n8)><(?P<n9>[_0-9a-zA-Z]+)>(.*)</(?P=n9)><(?P<n10>[_0-9a-zA-Z]+)>(.*)</(?P=n10)><(?P<n11>[_0-9a-zA-Z]+)>(.*)</(?P=n11)></(?P=n2)></(?P=n1)>',
    '<table><tr><th>序号</th><th>股票代码</th><th>股票简称</th><th>涨跌幅</th><th>换手率</th><th>最新价(元)</th><th>前期高点</th><th>前期高点日期</th><th>添加自选</th></tr></table>')

if match_obj:
    #groupdict()以字典格式显示别名和别名对应的匹配出字符串中标签名
    print(match_obj.groupdict())
    #groups()将分组内容以元组格式显示
    print(match_obj.groups())
    print(match_obj.group(0))
    for i in range(20):
        print(f'n{i + 1}', match_obj.group(i + 1))
else:
    print('匹配失败')
