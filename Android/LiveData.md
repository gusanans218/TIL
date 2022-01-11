1. 기존의 문제 : 기존에는 db에서 뭔가를 가져오거나 추가, 삭제할때마다 일일히 ui를 업데이트 해줘야 했다. 추가로 삭제나 추가가 오래걸린다면 화면상에는 보이지 않는다는 문제도 있다

2. LiveData와 MutableLiveData의 차이 : MutableLiveData는 수정이 가능
 LiveData는 수정이 불가능

3. MVVM 패턴에서의 LiveData 예시 : Repository(ViewModel) 에서 api 요청 등 을 통해 MutableLiveData에 값을 넣어주면 LiveData에도 넣어주는것이 된다. 
코드 예 )
private val _live = MutableLiveData<Int>()
val live : LiveData<Int>
	get() = _live

이렇게 코드를 짜면 _live의 값이 바뀔때 (_live.value = 0)
live의 value 또한 0이 된다
액티비티는 live를 관찰하고 있는데 _live가 바뀌면 live도 바뀌므로 이 라이브데이터를 관찰하는 곳에서는 
값이 바뀌었다는 사실을 알고 UI를 업데이트 한다

live를 관찰하고 있는 액티비티에서는 옵저빙을 한다
viewModel.live.observe(액티비티면 this 프래그먼트면 viewLifeCycleOwner를 사용해주면 된다.  ,{
      live의 값으로 뭔가 일을 수행
}


//회원가입 비밀번호 길이 제한하는 법

binding.pw.text.toString().trim().count >= 8 && binding.pw.text.toString().trim().count <= 20
이걸로 해도 되고
아니면 binding.pwInputLayout.error == null


위는
8글자랑 20글자
둘다 잡고
아래는 20글자만 잡고

