### API Routes

-   Next.js에서 API를 구축할 수 있게 하는 기능
-   src/pages/api 내부에서 ts 파일을 만들게 되면 동작하게 됨
-   /api/hello로 접속한 경우 json 데이터를 확인할 수 있음
-   자주 사용되지 않는 기능으로 더 자세한 사항은 next 공식 문서를 통해 확인 가능

```js
// Next.js API route support: https://nextjs.org/docs/api-routes/introduction
import type { NextApiRequest, NextApiResponse } from "next";

type Data = {
    name: string,
};

export default function handler(
    req: NextApiRequest,
    res: NextApiResponse<Data>
) {
    res.status(200).json({ name: "John Doe" });
}
```
