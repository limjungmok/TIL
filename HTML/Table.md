#** Table **
> 테이블 형식의 데이터를 만들 때 사용한다<br>
> Row(행, 좌우 한줄), Col(열,위아래 한줄) 이용하여 데이터를 입력한다<br>
> <tr> 태그를 이용해 좌우로 한 줄을 만들고 <br>
> <td> 태그를 이용해 상하로 한 줄을 만든다.<br>

---

```
<table>
  <thead>
    <tr>
      <td>학교</td>
      <td>학과</td>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>서울대학교</td>
      <td>컴퓨터공학</td>
    </tr>
    <tr>
      <td>세종대학교</td>
      <td>경영학과</td>
    </tr>
  </tbody>
</table>
```

* td 내에서 rowspan을 이용해 행을 확장하고, colspan을 이용해 열을 확장할 수 있다.
