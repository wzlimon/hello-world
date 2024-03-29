# hello-world

2019年5月29日

今天开始玩这个，挺有意思。

再试试

2020年4月10日

最近在学习python和flask

学习用手机登录管理

2020年4月11日
继续学习GIT，怎么上传更新
test for pycharm
test

用pycharm 直接PUSH失败，还是得用代码操作。

2020年4月12日
学习使用GIT指令操作来推送更新。

2020年4月12日
通过手机修改测试。

学习FLASK是从 http://www.helloflask.com 的《[Flask 入门教程](http://www.helloflask.com/tutorial/)》开始的，感谢 [@greyli](https://github.com/greyli)

学无止境。

再测试手机编辑修改。

 
三改手机

一个问题：修改不同步的错误怎么办？

DEV下的修改。看能不能影响到别的分支。

在写项目的时候习惯创建一个dev分支用于更新代码，等到整个或者阶段性完成的时候再合并到master上

步骤如下

```# 切换到master分支
git checkout master

# 将dev分支的代合并到master
git merge dev

# 查看状态
git status

# 推送
git push origin master
```

测试一下。
# 2020-4-13，办公室
test from office room.

测试通过SSH来更新GIT。

pycharm 用图标方式提交PUSH还是不行，需要通过代码来完成推送。

头像图标的`含义`。
---
![图标](http://www.cnun.com/images/LI-LOGO-V-40.png)

`L`:LIMON的首字母，`i`:右上角是引用语言的图标，代表社交。

    **近期学习的内容有：**
    * python 基础知识，正则运算符，数据库操作，爬虫编程
    * flask 基础知识，简单网页制作，数据库记录展示，翻页显示
    * CSS 基础知识复习和应用
    * Bootstrap 的基本应用
    * MSSQLSERVER 数据库导出转为 MYSQL格式
    * ASP网站改为PHP语言
    * 钉钉群聊机器人代码学习

* 收藏一篇[GIT教程](https://www.liaoxuefeng.com/wiki/896043488029600) 

* 继续复习，[设置SSH](https://www.jianshu.com/p/3f4b2ede5a93)

* 继续保存。   

    * 再试一下分支。 看一下MASTER分支。
    * 测试分支冲突解决方法。成功。
    * 测试了一下分支的关闭。

* 改为SSH模式 GIT Remotes ，免得每次更新要输入密码。

### 新建分支

建立一个分支HTML，新建一个INDEX.HTML文件，上传

```
git push --set-upstream origin html
```
网上已经有了

切换回MASTER，MERGE CHANGES后，再上传。

通过本地VCS同样可以删除运程的分支。

# 2020-04-14

生产系统数据库转换导出成功。

学习FASTADMIN看插件设计手册。 https://doc.fastadmin.net/developer/56.html 

# 2020-04-17

学习FASTADMIN对数据库的操作。

# 2020-04-18

修改生产系统数据结构。优化数据机构。

```
3、在任意表单页面添加如下代码，实现多选列表
<input id="c-category_ids" data-rule="" data-source="category/selectpage" data-params='{"custom[type]":"bm","isTree":1}' data-multiple="true" class="form-control selectpage" name="category_ids" type="text" value="{$row['category_ids']|htmlentities}">
```

数据限制
在后台开发的过程中经常会有这样的一个需求，每个管理员单独管理自己添加的数据或单独管理自己下级管理员添加的数据，管理员之间的数据是不相通的，每个管理员看到的数据是不同的。在FastAdmin中可以很方便的实现此功能。

首先我们需要在当前控制器添加以下两个属性
```
protected $dataLimit = 'auth'; //默认基类中为false，表示不启用，可额外使用auth和personal两个值
protected $dataLimitField = 'admin_id'; //数据关联字段,当前控制器对应的模型表中必须存在该字段

$dataLimit = false; //表示不启用，显示所有数据
$dataLimit = 'auth'; //表示显示当前自己和所有子级管理员的所有数据
$dataLimit = 'personal'; //表示仅显示当前自己的数据
$dataLimitField字段默认为admin_id，请注意添加该字段类型为int(10)。
```
通过以上配置后，在列表加载数据的时候将默认添加条件过滤不属于自己权限的数据，同时在添加时会自动维护admin_id的数据，在编辑、删除的时候会自动控制权限避免越权操作。

如果需要将原有的数据加入到FastAdmin后台管理权限控制当中，比如已有的数据已经有标识归属，但这个归属体系并非是FastAdmin的后台管理员体系。在这个时候我们就需要重写基类的getDataLimitAdminIds方法，将此方法返回数据标识的归属ID数组集合，这样即可使用FastAdmin的后台管理权限进行管理。

# 2020－04－21

注册了一台阿里云服务器
关于FASTADMIN数据导入，有这样一个设置

```
1. 在你的控制器中继承import方法，如下

public function import(){
        return parent::import();
}
在index.html中的build_toolbar方法添加import，如下
{:build_toolbar('refresh,add,edit,del,import')}
在模块对应的JS中添加import_url，如下
Table.api.init({
                extend: {
                    index_url: 'example/index',
                    add_url: 'example/add',
                    edit_url: 'example/edit',
                    del_url: 'example/del',
                    import_url: 'example/import',
                    multi_url: 'example/multi',
                    dragsort_url: '',
                    table: 'category',
                }
});
```
# 2020-04-22
继续玩阿里云，调试系统转码到FAST

# 2020-04-25
在阿里云调试资产系统，在FAST框架下逐步定制改码。解决了几个小BUG
BUG0425

1、CATEGORY_ID保存错误，ADMIN_ID误存为CATEGORY_ID，已经解决，在ADD里面有一个自动保存功能，PERSON功能下对应的字段不同，要修改。

2、三级公司无法添加客户，已经解决，直接修改TREE，增加取出父ID功能。

3、回收站功能错误，无法逐项还原、销毁。解决，字段名大写在JS中引用出错，全部统一改小写。

4、编辑功能错误，无法使用。解决，字段大写改小写后，HTML需修改。

5、客户信息导入功能不行。解决。导入要点，默认是关闭的，要增加三个地方的代码，EXCEL表头要使用备注名全称，包括ENUM中的说明，用EXCEL2007版转入，不要使用导出的表。

# 2020-04-26
在阿里云继续调试资产系统，生成收款台账。
MYSQL多表连接更新比较方便。

# 2020-04-27
问题：1、添加的关联字段排序错误。
2、A－B－C三表关联方法调试未成功。
# 2020－04－28
解决：1、关联字段排序错误是因为字段名重复引起的，2、采取修改数据结构，增加辅键方式暂时解决。
```
data-source="yjgxhttz/index"  data-field="htmc"
```
# 2020-04-30 
解决了详情页关联查询显示信息的问题，采取卡片式多页显示方便展示。图片显示功能未知。
```
    public function detail($ids)
    {
        $row = $this->model->where(['id' => $ids])->find();
        if (!$row)
            $this->error(__('No Results were found'));
        $this->view->assign("row", $row);
        $this->view->assign("row2", $row['admin']);
        return $this->view->fetch();
    }
```
# 2020-05-04
解决了自动编号中的一些问题

```
    /**
    *自动填写资产编号
    **/
    public function zcbhpicker($categoryid=null){
        $this->relationSearch = true;
        $newzcbh='';
        $list = $this->model
                ->with('category')
                ->where(['category_id' => $categoryid])
                ->order(['zcbh'],['desc'])
                ->field(['zcbh'])
                ->select();

        if (!$list){
            $this->model = model('Category');
            $row = $this->model->where(['id' => $categoryid])->find();
            $newzcbh='GTZC-'. $row['keywords'] . Date('Y') . '00001';
        }else{
            foreach ($list as $row) {
				$row->getRelation('category')->visible(['keywords']);
            }
            $list = collection($list)->toArray();
            foreach ($list as $row){
            $tmpzcbh=$row['zcbh'];
            break;
            }
            $tmpzcbh1=substr($tmpzcbh,0,9);
            $tmpzcbh2=substr($tmpzcbh,10,4);
            if ($tmpzcbh2 < Date('Y')){
                $newzcbh=$tmpzcbh1.Date('Y').'00001';
            }else{
                $tmpzcbh3=substr($tmpzcbh,15,5);
                $i=intval($stmpzcbh3);
                $i=$i+1;
                $tmpzcbh4=substr(str_repeat("0",5).$i,-5,5);
                $newzcbh=$tempzcbh1.Date('Y').$tempzcbh4;
            }
        }
        $this->success("", null, ['czcbh' => $newzcbh]);
        return ;
    }

```
# 2020-05-05
单位、地块、房产、资产、客户、合同、收款共七张表格的录入流程调试基本完成。
因FASTADMIN的局限，学习还未深入，暂时无法实现三表关系。暂时通过反向更新方式来确保一对一的关系 。
```

                    if ($params['status'] =='1') {
                    $res = Db::name('yjgxzctz')->where('id',$params['yjgxzctz_id'])->setField(['yjgxhttz_id'=>$ids,'yjgxkhtz_id'=>$params['yjgxkhtz_id'],'status'=>$params['status']]);
                    $this->success();
                    }


```
# 2020-5-10
简单的JS联动难倒了。
提取当前ID =>$this->model->id

# 2020-05-17
解决了GROUP统计问题

```
            list($where, $sort, $order, $offset, $limit) = $this->buildparams();
            $total = $this->model
                    ->with(['admin','category'])
                    ->where($where)
                    ->order($sort, $order)
                    ->count();
            $subsql = Db::name('yjgxhttz')->field('yjgxkhtz_id,count(CASE WHEN status="1" THEN 1 ELSE NULL END)  count')->group('yjgxkhtz_id')->buildSql();

            $list = $this->model
                    ->with(['admin','category'])
                    ->join([$subsql=> 'w'], 'yjgxkhtz.id = w.yjgxkhtz_id','left')
                    ->field('w.count as count)
                    ->where($where)
                    //->group('id')
                    ->order($sort, $order)
                    ->limit($offset, $limit)
                    ->select();

            foreach ($list as $row) {
                $row->visible(['id','zllb','zcbh','name','address','area','type','status','about','images','landid','houseid','yjgxhttz_id','yjgxkhtz_id','category_id','count']);
                $row->getRelation('admin')->visible(['nickname']);
				$row->getRelation('category')->visible(['nickname']);

            }
            $list = collection($list)->toArray();
            $result = array("total" => $total, "rows" => $list);

            return json($result);
        }
        return $this->view->fetch();
```


另，数据结果导出代码

```
SELECT
COLUMN_NAME 列名,
COLUMN_TYPE 数据类型,
DATA_TYPE 字段类型,
CHARACTER_MAXIMUM_LENGTH 长度,
IS_NULLABLE 是否为空,
COLUMN_DEFAULT 默认值,
COLUMN_COMMENT 备注
FROM
INFORMATION_SCHEMA.COLUMNS
where
-- developerclub为数据库名称，到时候只需要修改成你要导出表结构的数据库即可
table_schema ='developerclub'
AND
-- article为表名，到时候换成你要导出的表的名称
-- 如果不写的话，默认会查询出所有表中的数据，这样可能就分不清到底哪些字段是哪张表中的了，所以还是建议写上要导出的名名称
table_name = 'article'
```
# 2020-05-18
今天推出新代码测试，发放用户账号。
数据导入，时间格式需要修改为2020-05-18格式。
准备编写教程。

# 2020-05-21
合并多条为一条

```
update fa_yjgxzctz a,  (SELECT YWBH, group_concat(url) as urls FROM  yjgx_业务附件 GROUP BY YWBH ORDER BY YWBH ) b set a.files=b.urls where a.zcbh=b.YWBH 
```
# 2020-05-24
完成了合同自动调整状态和资产状态改变。
进行了实时统计数据的显示，并实现了单面统计。

```
function index(){
        //设置过滤方法
        $this->request->filter(['strip_tags']);
        if ($this->request->isAjax()) {
            //如果发送的来源是Selectpage，则转发到Selectpage
            if ($this->request->request('keyField')) {
                return $this->selectpage();
            }
            list($where, $sort, $order, $offset, $limit) = $this->buildparams();
            $total = $this->model
                ->where($where)
                ->order($sort, $order)
                ->count();

            $list = $this->model
                ->where($where)
                ->order($sort, $order)
                ->limit($offset, $limit)
                ->select();

            $list = collection($list)->toArray();
            $result = array("total" => $total, "rows" => $list);

            //处理统计
            if(!empty($result['rows'])){

                //提取所有字段名称
                $filed_arr = array_keys($result['rows'][0]);

                //处理数据
                $total = [];

                foreach ($filed_arr as $filed_key){
                    $total[$filed_key] = array_sum(array_column($result['rows'], $filed_key));//合计
                }

                //设置标题
                $total['id'] = '合计';

                //追加到头部
                array_unshift($result['rows'],$total);
//                array_unshift($result['rows'],$ratio);

                //追加到尾部
//                $result['rows'][] = $total;
//                $result['rows'][] = $ratio;
            }
            
        }
        return $this->view->fetch();
    }
```
# 2020-05-28
解决了A－B－C三级关联显示问题，但查询还需作研究。
应用系统全面推广试运行，一周来解决了大量的基础数据缺失问题。
编写简明操作手册。

# 2020-06-03
完成第一稿手册，并下发各单位。

# 2020-06-07
完成了统计报表的保存和列表展示，为下一步统计图打下基础。

# 2020-06-09
完成了echarts的统计数据调用和展示，完善了各数据表格之间的链接导航。

# 2020-06-12
下发通知，要求完善信息资料。合同模板在线生成电子合同试点成功。向GZ、JC等单位开放部分账号。

# 2020-07-05
数据更新一段落，重启代码更新工作。以下是预览图显示的官方代码

```
<ul class="row list-inline plupload-preview" data-template="mytpl" id="p-image"></ul>

<script type="text/html" id="mytpl">
<li class="col-xs-3"><a href="<%=fullurl%>" data-url="<%=url%>" target="_blank" class="thumbnail"><img src="<%=fullurl%>" onerror="this.src='https://tool.fastadmin.net/icon/'+'<%=fullurl%>'.split('.').pop()+'.png';this.onerror=null;" class="img-responsive"></a><a href="javascript:;" class="btn btn-danger btn-xs btn-trash"><i class="fa fa-trash"></i></a></li>
</script>
```
# 2020-7-06

```
update fa_yjgxhttz a ,fa_yjgxzctz b set a.yjgxzctz_id=b.id where a.zcbh=b.zcbh and a.id>6755 and a.category_id=16

update fa_yjgxzctz a ,fa_yjgxhttz b set a.yjgxhttz_id=b.id, a.yjgxkhtz_id=b.yjgxkhtz_id where a.id=b.yjgxzctz_id and a.id>6811 and a.category_id=16

```
# 2020-07-08
偶尔看到2008年写的工资系统代码，很想把这个系统升级一下。

```
nowrap="nowrap"
```

# 2022-3-7
重新拿起这些代码去看，一点都看不懂了。一年半时间忘光了。
