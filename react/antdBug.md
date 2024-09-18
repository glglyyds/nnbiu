**react–antd TreeSelect树形选择异步懒加载**
```jsx
import React, {useState} from "react";
import { TreeSelect } from 'antd';
function APP(){
    const [roleId, newRoleId] = useState();
    const [treeData, setTreeData] = useState([
        {
            id: '046f0000-7749-a4fc-8025-08daa2b19ec4',
            key:"046f0000-7749-a4fc-8025-08daa2b19ec4",
            pId: 0,
            roleName: '超级管理员',
            isLeaf:false,
        }
    ]);
    const genTreeNode = (parentId) => {
        RoleList({rpid:parentId}).then(res=>{
            if(res!=null && res.roleList.length>0){
                let aa = []
                res.roleList.forEach(item=>{
                    aa.push({
                        id: item.id,
                        key:item.id,
                        pId: item.rpid,
                        roleName: item.roleName,
                        isLeaf:!item.hasChildren
                    })
                })
                setTreeData(
                    treeData.concat(aa),
                );
            }
        })
    };
    const onLoadData = ({ id }) =>
        new Promise((resolve) => {
            genTreeNode(id)
            resolve(undefined);
        });
    const onChange = (newValue) => {
        console.log(newValue);
        newRoleId(newValue);
    }
    return(
         <TreeSelect
            fieldNames={{
                value: 'id',
                label: 'roleName',
                title: 'roleName',
            }}
            value={roleId}
            treeDataSimpleMode
            placeholder="请选择上级角色"
            onChange={onChange}
            loadData={onLoadData}
            treeData={treeData}
        />
    )
}
export default APP
```