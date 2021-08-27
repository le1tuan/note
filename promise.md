có đoạn code sau
```
const handleFetch = async () => {
    const arr = await getAsync();
    let temp = null;
    const newArr = await Promise.all(
      arr.map(async (item) => {
        console.log("---->", { ...cache });
        if (cache[item]) {
          temp = await cache[item];
          console.log("get cache temp", temp);
        } else {
          const resultP = asyncCall(item);
          ////////============noteeee/////
          cache[item] = resultP;
          temp = await resultP;
        }
        return temp;
      })
    );
    console.log("done1", newArr);
    setList(newArr);
  };
```
Tại sao đoajn comment note kia laij không await luôn mà lại để không.
Vì nếu await sẽ stop phía bên dưới add value vào cache varible
và làm cho điều kiejen lúc nào cũng nhảy vào else
