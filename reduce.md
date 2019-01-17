# reduce
I. Giải thích
- lặp qua từng phần tử của array.
-  ví dụ: [1,2,3,4].reduce((acc, current) => acc + current)
- acc = 1, current 2 => return 3
- acc =3, current = 3 => return 6
- acc = 6, current = 4 => return 10
- => return 10
# compose và pipe
I. pipe
- pipe giúp combine các call function 
- ví dụ: H muốn lấy tên 1 người, viết hoa tên đấy, lấy 6 ký tự đầu, đảo ngược
  - const name =  getName()
  - const upperCaseName = upperCaseName(name)
  - const 6characters = get6Characters(upperCaseName)
  - const reverseName = reverse(6characters)
  - Dài dòng
- pipe(
  getName,
  upperCaseName,
  get6Characters,
  reverse
)(name)
- Dùng reduce viết pipe :
  - const pipe = (...functions) => (name) => {
    return functions.reduce((acc, current) => {
      return current(acc)
    }, name)
  }

  pipe(
    (v) => v,
    (v) => `------> ${v}`,
    (v) => `======>  ${v}`,
  )('letuananh')
  
  
  
  
function deepEqual(source, target) {
 const keys = Object.keys(source)
 for(let i = 0 ; i < keys.length ; i++) {
   	const key = keys[i];
 	if (target[key]) {
      if (typeof target[key] === 'object' && typeof source[key] === 'object') {
       	return deepEqual(source[key], target[key])
      } else if (target[key] === source[key]) {
      	return true	
      }
    }
   return false;
 }
}



- top : cách container bao nhiêu pixel
- transform: translate : đơn vị phần trăm là phần trăm theo độ dài hoặc rộng của element mình transform
