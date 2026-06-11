# happ-geo

Готовый профиль маршрутизации для [Happ](https://www.happ.su) (iOS / Android / macOS / Windows / Linux): весь трафик через VPN, кроме российских сервисов и Apple/Microsoft/Steam. DNS: Cloudflare `1.1.1.1` over DoH.

## Установка

1. Установить Happ на своё устройство — ссылки на все платформы на [happ.su](https://www.happ.su).
2. Тапнуть ссылку ниже на устройстве (или скопировать и импортировать в Happ → Routing → Import from clipboard):

```
happ://routing/onadd/eyJOYW1lIjoiUm9zY29tVlBOLVBlcnNvbmFsIiwiR2xvYmFsUHJveHkiOiJ0cnVlIiwiVXNlQ2h1bmtGaWxlcyI6InRydWUiLCJSZW1vdGVEbnMiOiIxLjEuMS4xIiwiRG9tZXN0aWNEbnMiOiIxLjEuMS4xIiwiUmVtb3RlRE5TVHlwZSI6IkRvSCIsIlJlbW90ZUROU0RvbWFpbiI6Imh0dHBzOi8vMS4xLjEuMS9kbnMtcXVlcnkiLCJSZW1vdGVETlNJUCI6IjEuMS4xLjEiLCJEb21lc3RpY0ROU1R5cGUiOiJEb0giLCJEb21lc3RpY0ROU0RvbWFpbiI6Imh0dHBzOi8vMS4xLjEuMS9kbnMtcXVlcnkiLCJEb21lc3RpY0ROU0lQIjoiMS4xLjEuMSIsIkdlb2lwdXJsIjoiaHR0cHM6Ly9jZG4uanNkZWxpdnIubmV0L2doL25vdmV2OS9oYXBwLWdlb0BiYjk2YzE3M2ZhNzMxYjkxMDk3NDZlNGIyNWI3NTJkNzg0MzBlNmVjL2dlb2lwLmRhdCIsIkdlb3NpdGV1cmwiOiJodHRwczovL2Nkbi5qc2RlbGl2ci5uZXQvZ2gvbm92ZXY5L2hhcHAtZ2VvQGJiOTZjMTczZmE3MzFiOTEwOTc0NmU0YjI1Yjc1MmQ3ODQzMGU2ZWMvZ2Vvc2l0ZS5kYXQiLCJMYXN0VXBkYXRlZCI6IjE3NzY1ODAwMDAiLCJEbnNIb3N0cyI6eyJsa2ZsMi5uYWxvZy5ydSI6IjIxMy4yNC42NC4xNzUiLCJsa25wZC5uYWxvZy5ydSI6IjIxMy4yNC42NC4xODEifSwiUm91dGVPcmRlciI6ImJsb2NrLXByb3h5LWRpcmVjdCIsIkRpcmVjdFNpdGVzIjpbImdlb3NpdGU6cHJpdmF0ZSIsImdlb3NpdGU6Y2F0ZWdvcnktcnUiLCJnZW9zaXRlOndoaXRlbGlzdCIsImdlb3NpdGU6bWljcm9zb2Z0IiwiZ2Vvc2l0ZTphcHBsZSIsImdlb3NpdGU6ZXBpY2dhbWVzIiwiZ2Vvc2l0ZTpyaW90IiwiZ2Vvc2l0ZTplc2NhcGVmcm9tdGFya292IiwiZ2Vvc2l0ZTpzdGVhbSIsImdlb3NpdGU6dHdpdGNoIiwiZ2Vvc2l0ZTpwaW50ZXJlc3QiLCJnZW9zaXRlOmZhY2VpdCIsImRvbWFpbjptYWduaXQucnUiLCJkb21haW46bWdjLWxveWFsdHkucnUiXSwiRGlyZWN0SXAiOlsiZ2VvaXA6cHJpdmF0ZSIsImdlb2lwOmRpcmVjdCJdLCJQcm94eVNpdGVzIjpbImdlb3NpdGU6Z29vZ2xlLXBsYXkiLCJnZW9zaXRlOmdpdGh1YiIsImdlb3NpdGU6dHdpdGNoLWFkcyIsImdlb3NpdGU6eW91dHViZSIsImdlb3NpdGU6dGVsZWdyYW0iXSwiUHJveHlJcCI6W10sIkJsb2NrU2l0ZXMiOlsiZ2Vvc2l0ZTp3aW4tc3B5IiwiZ2Vvc2l0ZTp0b3JyZW50IiwiZ2Vvc2l0ZTpjYXRlZ29yeS1hZHMiXSwiQmxvY2tJcCI6W10sIkRvbWFpblN0cmF0ZWd5IjoiSVBJZk5vbk1hdGNoIiwiRmFrZUROUyI6ImZhbHNlIn0=
```

3. Подключить VPN (нужна своя подписка — этот репо её не содержит).

## Direct-исключения для российских приложений

Некоторые российские сервисы (банки, ритейл) **блокируют доступ с иностранных IP** или детектят VPN, поэтому их домены добавлены в `DirectSites`, чтобы шли мимо VPN с реального РФ-IP:

- `domain:magnit.ru`, `domain:mgc-loyalty.ru` — приложение Магнит (у него есть встроенный VPN-детектор; через VPN не работает).

Если ещё какое-то РФ-приложение перестало работать при включённом VPN — найди его домены (в логе соединений Happ или статикой из APK) и добавь `domain:<host>` в `DirectSites`.

## Источники

Geo-файлы — зеркало [hydraponique/roscomvpn-geosite](https://github.com/hydraponique/roscomvpn-geosite) (MIT) и [roscomvpn-geoip](https://github.com/hydraponique/roscomvpn-geoip), запинены по коммиту для стабильности.

Лицензия: MIT ([LICENSE](./LICENSE)).
