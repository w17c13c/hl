import json
import datetime
from typing import List, Dict, Optional
import matplotlib.pyplot as plt
 
class AppleCiderVinegarApp:
    def __init__(self):
        self.users = {}  # 存储用户数据 {user_id: user_data}
        self.current_user = None
        self.load_data()
    
    def load_data(self):
        """从文件加载数据"""
        try:
            with open('acv_data.json', 'r') as f:
                data = json.load(f)
                self.users = data.get('users', {})
        except FileNotFoundError:
            pass
