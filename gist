# step1 - hashlibをimportする
import hashlib

# step2 - class "GeekCoinBlock" を作成
class GeekCoinBlock:
    
    def __init__(self, previous_block_hash, transaction_list):

        self.previous_block_hash = previous_block_hash
        self.transaction_list = transaction_list

        self.block_data = f"{' - '.join(transaction_list)} - {previous_block_hash}"
        self.block_hash = hashlib.sha256(self.block_data.encode()).hexdigest()

# step3 - hashlibの仕組みを説明
In [1]: import hashlib

In [2]: message = "Python is great"

In [3]: h1 = hashlib.sha256(message.encode())

In [4]: h1
Out[4]: <sha256 ... object @ 0x7efcd55bfbf0>

In [5]: h1.hexdigest()
Out[5]: 'a40cf9cca ... 42ab97'

In [6]: h2 = hashlib.sha256(b"Python is not great")

In [7]: h2
Out[7]: <sha256 ... object @ 0x7efcd55bfc90>

In [8]: h2.hexdigest()
Out[8]: 'fefe510a6a ... 97e010c0ea34'

# step4 - トランザクションを作成
class GeekCoinBlock:
    ...

t1 = "Noah sends 5 GC to Mark"
t2 = "Mark sends 2.3 GC to James"
t3 = "James sends 4.2 GC to Alisson"
t4 = "Alisson sends 1.1 GC to Noah"

# step5 - ブロック1を作成
block1 = GeekCoinBlock('firstblock', [t1, t2])

print(f"Block 1 data: {block1.block_data}")
print(f"Block 1 hash: {block1.block_hash}")

# step6 - ブロック2を作成
block2 = GeekCoinBlock(block1.block_hash, [t3, t4])

print(f"Block 2 data: {block2.block_data}")
print(f"Block 2 hash: {block2.block_hash}")

# step7 - 作成したブロックをブロックチェーンにするクラスを作成
# main.py

class Blockchain:
    def __init__(self):
        self.chain = []
        self.generate_genesis_block()

    def generate_genesis_block(self):
        self.chain.append(GeekCoinBlock("0", ['Genesis Block']))
    
    def create_block_from_transaction(self, transaction_list):
        previous_block_hash = self.last_block.block_hash
        self.chain.append(GeekCoinBlock(previous_block_hash, transaction_list))

    def display_chain(self):
        for i in range(len(self.chain)):
            print(f"Data {i + 1}: {self.chain[i].block_data}")
            print(f"Hash {i + 1}: {self.chain[i].block_hash}\n")

    @property
    def last_block(self):
        return self.chain[-1]
        
# step8 - 完成したブロックチェーンをテストしてみる
# main.py

import hashlib

class GeekCoinBlock:
    ...


class Blockchain:
    ...

t1 = "George sends 3.1 GC to Joe"
t2 = "Joe sends 2.5 GC to Adam"
t3 = "Adam sends 1.2 GC to Bob"
t4 = "Bob sends 0.5 GC to Charlie"
t5 = "Charlie sends 0.2 GC to David"
t6 = "David sends 0.1 GC to Eric"

myblockchain = Blockchain()

myblockchain.create_block_from_transaction([t1, t2])
myblockchain.create_block_from_transaction([t3, t4])
myblockchain.create_block_from_transaction([t5, t6])

myblockchain.display_chain()     
