## Hi there 👋

import requests

username = "SciLejkeee"
url = f"https://www.codewars.com/api/v1/users/{username}"

response = requests.get(url)
data = response.json()

with open("README.md", "w") as readme:
    readme.write(f"## 🏆 Codewars Achievements\n\n")
    readme.write(f"- **Username**: [{username}](https://www.codewars.com/users/{username})\n")
    readme.write(f"- **Total Honor**: {data['honor']}\n")
    readme.write(f"- **Kata Completed**: {data['codeChallenges']['totalCompleted']}\n")
    readme.write(f"- **Current Rank**: {data['ranks']['overall']['name']}\n")
