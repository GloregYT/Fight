import random


class Player:

    def __init__(self, name, health=100, attack=10):
    
        self.name = name
        
        self.health = health
        
        self.attack = attack

    def fight(self, monster):
    
        print(f"{self.name} начинает бой с {monster.name}!")

        while self.health > 0 and monster.health > 0:
        
            # Атака игрока
            
            damage_to_monster = random.randint(1, self.attack)
            
            monster.health -= damage_to_monster
            
            print(f"{self.name} атакует {monster.name}, нанося {damage_to_monster} урона!")

            if monster.health <= 0:
            
                print(f"{monster.name} побежден!")
                
                break

            # Атака монстра
            
            damage_to_player = random.randint(1, monster.attack)
            
            self.health -= damage_to_player
            
            print(f"{monster.name} атакует {self.name}, нанося {damage_to_player} урона!")

            if self.health <= 0:
            
                print(f"{self.name} побежден!")

        print("Бой завершен.")


class Monster:

    def __init__(self, name, health=50, attack=8):
    
        self.name = name
        
        self.health = health
        
        self.attack = attack



        player = Player("Герой")

        monster = Monster("Гоблин")

        player.fight(monster)
