# ViewType

## 뷰 타입(View Type)은 **RecyclerView에서 다양한 레이아웃을 가진 아이템을 구분**하기 위한 방식.

`getItemViewType()` 메서드에서 각 아이템의 **뷰 타입을 반환**하고, `onCreateViewHolder()`에서 **뷰 타입에 따라 적절한 레이아웃과 ViewHolder**를 인플레이트하여 사용한다.

호출 순서

1. getItemViewType 호출
- 뷰타입을 결정하기 위에 맨 처음으로 호출
2. onCreateViewHolder 호출
- 뷰를 생성하기 위해 호출
- → viewType 파라미터를 통해 어떤 viewholder를 생성할지 결정한다.
- viewType에 따라 레이아웃 파일을 인플레이트하고 각 viewholder를 생성
3. onBindViewHolder 호출
- viewholder에 맞는 데이터를 바인딩하기 위해 호출

recycler가 처음으로 아이템을 렌더링 할떄

- getItemViewType
- onCreateViewHolder
- onBindViewHolder

RecyclerView가 스크롤 되거나 아이템이 변경될 때

- getItemViewType
- onCreateViewHolder (뷰 재사용이 가능하다면 호출되지 않고 기존의 viewholder를 재사용)
- onBindViewHolder

DiffUtil.ItemCallback를 통해 데이터의 차이를 계산하고 불필요한 뷰 업데이트를 방지하도록 돕는다.

`areItemsTheSame`과 `areContentsTheSame`이 있다