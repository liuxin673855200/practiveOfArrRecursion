# 
let authList = [
  {
    name: "view",
  },
  {
    name: "untility",
    children: [
      {
        name: 'dataImport',
        children: [
          {
            name: "basinImport",
          },
          {
            name: "blockImport",
          }
        ]
      },
      {
        name: 'dataManagement',
        children: [
          {
            name: "blockManagement",
          }
        ]
      }
    ]
  },
];

let newArr=[
    {
        name: 'view',
    },
    {
        name: 'untility',
        // redirect: '/untility/dataImport',
        children: [
            {
                name: 'basinImport',
            },
            {
                name: 'blockImport',
            },
            {
                name: 'regionImport',
            },
            {
                name: 'fieldImport'
              }
              ]
      }
]

let getArr=(Arr)=>{
  var new_arr=[]
  for(var i=0;i<Arr.length;i++){
    new_arr.push(Arr[i].name)
    if(!!Arr[i].children){//如果存在child
      getArr(Arr[i].children)
    }
  }
  return new_arr
}
console.log(getArr(authList))
