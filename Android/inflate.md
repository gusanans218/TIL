# inflate

**XML로 정의된 레이아웃 파일을 실제 뷰 객체로 변환하는 과정**

```
CellUserAddBinding.inflate(LayoutInflater.from(context), parent, false), onClickAddButton
```

## LayoutInflater (도구)

- XML 파일로 정의된 레이아웃을 “읽어서” 실제 뷰 객체로 만드는 것
- 레이아웃은 텍스트로 정의되어있고 이걸 화면에 보여주려면 뷰 객체로 변환해야하니까

- `val inflater = LayoutInflater.from(context)`

이런식으로 액티비티나 프레그먼트에서 사용할때는 인스턴스를 얻는다

## inflate() (도구를 사용해 변환하는 작업을 수행)

**XML 레이아웃 파일을 읽어서 뷰 객체로 변환**하는 작업을 수행합니다.

- `val itemView = inflater.inflate(R.layout.item_layout, parent, false)`
- inflate() 는 LayoutInflater의 메서드이기 때문에 layoutInflater 인스턴스를 통해서 호출해야한다