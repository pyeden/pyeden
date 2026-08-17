# Hi,I'm Future Deng! 👋
**自动化软件架构师**

<img src="https://github-readme-stats.vercel.app/api?username=pyeden&show_icons=true&theme=dark" alt="logo" height="160" align="right" width="50%" />

- 🔭 现在就职于 **赛力斯汽车有限公司**
- 👋 岗位职责
  - 负责团队技术规划和自动化测试体系建设
  - 主导设计自动化测试平台软件架构
  - 主导整车功能测试自动化测试方案开发
  - 主导ADS智能辅助驾驶自动化测试方案开发   
- 🌱 工作中常用技术栈
  - **Python、Golang、c++**
  - **React、Vue、Angular**
- ⚡ 研究方向: 
  - Web 服务器开发
  - 自动化测试开发
  - 大数据分析开发
  - NLP自然语言处理算法开发
  - 图像识别、检查算法开发

## Follow Me
[![个人博客](https://img.shields.io/badge/-个人博客（pyeden.com）-c14438?style=flat-square&logo=B&logoColor=white)](https://www.seres-ai.com/)
[![Github](https://img.shields.io/github/followers/pyeden?label=Github&style=social)](https://github.com/pyeden)

## Show Code
```python

from abc import ABC, abstractmethod

class Validator(ABC):
    """
    使用python描述器来验证名字是不是“future.deng”
    """

    def __set_name__(self, owner, name):
        self.private_name = '_' + name

    def __get__(self, obj, objtype=None):
        return getattr(obj, self.private_name)

    def __set__(self, obj, value):
        self.validate(value)
        setattr(obj, self.private_name, value)

    @abstractmethod
    def validate(self, value):
        pass


class ValidatorName(Validator):
    """
    使用类继承的方式实现validate方法
    """
    def __init__(self, is_validator_name=True):
        self.is_validator_name = is_validator_name

    def validate(self, value):
        if self.is_validator_name:
            if value != 'Future Deng':
                raise ValueError("Future Deng 的私人代码，必须传入'Future Deng' 才能被实例化")


class PythonWebEngineer:

    name = ValidatorName(is_validator_name=True)

    def __init__(self, name):
        self.name = name
        self.age = 28
        self.role = "Python Engineer"
        self.language_spoken = ["zh_CN", "en_US"]
        self.skill = ["Python", "React", "Golang"]


if __name__ == '__main__':
    me = PythonWebEngineer('Future Deng')
    me.name
    
# 输出结果
# Future Deng

#   me = PythonWebEngineer('Future Dengsss')
#   me.name

# 若是传入错误的值 'Future Dengsss'
"""
  File "/Users/futuredeng/opt/backendxh/dsz.py", line 161, in validate
    raise ValueError("Future Deng 的私人代码，必须传入'Future Deng' 才能被实例化")
ValueError: Future Deng 的私人代码，必须传入'Future Deng' 才能被实例化
"""



```
