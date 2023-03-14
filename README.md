# Youtube Clone Coding

## ✍목적

> 🧾 기본적인 React 웹사이트를 만들어 보기위해 드림코딩의 TODO앱 만들기 프로젝트를 클론코딩했습니다.

<br/>

## 🔨라이브러리 및 플러그인

<img src="https://img.shields.io/badge/React-61DAFB?style=for-the-badge&logo=React&logoColor=black"/> <img src="https://img.shields.io/badge/PostCSS-DD03A0A?style=for-the-badge&logo=PostCSS&logoColor=white"> <img src="https://img.shields.io/badge/uuid-black?style=for-the-badge">

<br/>

## 🚀기능

1. 아이템 추가하기

2. 아이템 삭제하기

3. 아이템 체크박스 효과

4. 아이템을 속성에 따라 필터링하기

5. 다크 모드 지원하기

6. 로컬 스토리지에 다크모드 저장하기

   <br/>

## 📺시연 영상

![todo](https://user-images.githubusercontent.com/105909450/224913351-b4524310-b780-4593-ac44-e9d1c9ae364a.gif)

  <br/>

## 📘배운 점

- Post CSS 사용하기
  1. 파일을 **파일이름.module.css**이름으로 생성한다.
  2. import styles(임의의 객체 이름) from ‘./Button1.module.css’;
  3. 클래스의 이름을 객체의 프로퍼티로 쓴다.
     > return <button className={styles.button}>Button1</button>;

<br/>

- 다크모드

      - useEffect() :  컴포넌트가 렌더링 이후에 어떤 일을 수행해야하는 지를 정할 수 있다. 기본적으로 첫번째 렌더링과 이후의 모든 업데이트에서 수행된다. 특정 값들이 리렌더링 시에 변경되지 않는다면 React로 하여금 effect를 건너뛰도록 할 수 있습니다. 해당 프로젝트에서는 딱 한 번씩만 실행하도록 useEffect의 두 번째 인수로 빈 배열을 썼다.

      - useContext() : darkMode와 toggleDarkMode 값을 모든 컴포넌트들이 공유할 수 있도록 한다.

      - localstorage에 앱에 적용된 theme 값(dark/light)을 저장한다.

      - prefers-color-scheme 미디어 쿼리를 사용하면 사용자의 시스템이 dark/light 테마를 감지하여 그에 해당되는 스타일을 적용할 수 있다.

      ```css
      @media (prefers-color-scheme: dark) {
        /*dark모드에 적용할 스타일을 정의*/
        }
      ```

<br/>

- 필터링하기 : Header와 TodoList 컴포넌트의 상위 컴포넌트인 App.jsx에서 filters 배열을 생성하고 useState함수를 사용하여 filter값을 보관하고 업데이트하도록 한다.

  ```javascript
  const filters = ['all', 'active', 'completed'];

  function App() {
  	const [filter, setFilter] = useState(filters[0]);
  	return (
  		<DarkModeProvider>
  			<Header filters={filters} filter={filter} onFilterChange={setFilter} />
  			<TodoList filter={filter} />
  		</DarkModeProvider>
  	);
  }
  ```

<br/>

- todos 배열을 localstoarge에 저장함

  > localstorage에는 문자형 데이터만 저장할 수 있다.
  > 따라서 배열 데이터를 저장할 때는 JSON.stringify() 함수를 사용하여 객체와 배열을 JSON 문자열로 변환하고, 읽어낼 때는 JSON.parse() 함수를 사용하여 원본 데이터를 얻는다.

  <br/>
