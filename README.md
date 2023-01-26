# -
http://www.jungol.co.kr/bbs/board.php?bo_table=pbank&amp;wr_id=3878

#include <stdio.h>
#define _CRT_SECURE_NO_WARNINGS

int main() {
	int ADDH = 0; //+60
	int ADDT = 0; //+10
	int MINT = 0; //-10
	int ADDO = 0; //+1
	int MINO = 0; //-1

	int time;
	printf("오븐을 얼마나 작동시킬까요?\n");
	scanf("%d", &time);
	int rm = time % 10;

	if (time < 0) {
		time = 0;
	}
	int rt = time;
	while (rt != 0) {
		if (rt >= 60) {
			rt = rt - 60;
			ADDH++;
		}
		else {
			int rq = rt / 10;
			if (rm > 5) {
				ADDT = ADDT + rq + 1;
				MINO = MINO + 10 - rm;
				rt = 0;
			}
			else if (rm <= 5) {
				ADDT = ADDT + rq;
				ADDO = ADDO + rm;
				rt = 0;
			}
		}
	}
	printf("오븐 동작 시간 : %d분\n", time);
	printf("%d %d %d %d %d", ADDH, ADDT, MINT, ADDO, MINO);
}
