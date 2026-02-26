# python-adventure-game
mport random

print("歡迎來到冒險者遊戲！")
player_hp = 100
monster_hp = 80

while player_hp > 0 and monster_hp > 0:
    print("\n你的血量:", player_hp)
    print("怪物血量:", monster_hp)

    action = input("選擇行動 (1.攻擊 2.防禦): ")

    if action == "1":
        damage = random.randint(10, 25)
        monster_hp -= damage
        print(f"你對怪物造成 {damage} 點傷害！")
    elif action == "2":
        print("你進入防禦狀態，減少傷害！")
    else:
        print("請輸入正確選項！")
        continue

    if monster_hp > 0:
        monster_damage = random.randint(5, 20)
        player_hp -= monster_damage
        print(f"怪物攻擊你 {monster_damage} 點傷害！")

if player_hp > 0:
    print("🎉 恭喜你打敗怪物！")
else:
    print("💀 你被怪物打敗了...")
