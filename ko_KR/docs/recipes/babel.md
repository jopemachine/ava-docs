___
**역자주**

이 문서는 [babel.md](https://github.com/avajs/ava/blob/main/docs/recipes/babel.md)의 한국어 번역입니다. [이곳](https://github.com/avajs/ava/compare/71404c23302d825095659c70cb9a1b08251697ad...main#diff-0730bb7c2e8f9ea2438b52e419dd86c9)에서 AVA의 master 브랜치와 이 문서의 차이를 확인할 수 있습니다. (만약 차이가 없다면 문서가 최신 버전임을 의미합니다)
___

# AVA 3에서 바벨 설정하기

**AVA 4 이상에선 지원되지 않습니다.**

`@ava/babel` 패키지를 설치함으로써 바벨을 활성화 할 수 있습니다, AVA 설정의 `babel`에 `true` 값을 추가하세요.

**`package.json`:**

```json
{
	"ava": {
		"babel": true
	}
}
```

[`@ava/babel`](https://github.com/avajs/babel)에서 더 많은 정보를 알아보세요.
