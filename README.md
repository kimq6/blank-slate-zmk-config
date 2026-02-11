# Blank Slate ZMK Firmware

This repo contains the firmware for the Blank Slate PCB.

For full build guide for the Blank Slate, see https://docs.lpgala.xyz/docs/blank-slate-build-guide/overview/

# Soft Off Support

Blank Slate includes support for a ZMK feature this is still [in a PR](https://github.com/zmkfirmware/zmk/pull/1942). By default, this repository builds against that feature branch to ensure that works properly.

Should you desire to track ZMK `main` (or some other branch of ZMK), simply edit the `config/west.yml` file and replace the contents with:

```
manifest:
  remotes:
    - name: petejohanson
      url-base: https://github.com/petejohanson
  projects:
    - name: zmk
      remote: zmkfirmware
      revision: main
      import: app/west.yml
    - name: blank-slate-zmk-module
      remote: petejohanson
      revision: main
  self:
    path: config
```

And then comment out the line in `config/lpgalaxy_blank_slate.conf`:

```
# CONFIG_ZMK_PM_SOFT_OFF=y
```

---
# 블루투스 접속이 안되는 경우
1. 기기에서 지우고 BLT_CLR
2. 빌드 다시깔기

# 설치
유선연결
reset 더블클릭(파란빛 스무드하게 열림)
lpgalaxy_blank_slate-zmk.uf2 (studio 아님)을 해당 장치에 붙여넣기
맥 기준 중간에 연결 끊겼다고 오류나는게 정상임