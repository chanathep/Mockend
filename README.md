# Mockend
git clone https://github.com/chanathep/Mockend.git

# Setup
Create a .mockend.json file with the following basic config on your repo:

github.com/org/repo/.mockend.json
{
  "User": {
    "title": { "string": {} }
  }
}
Try your new mock server:

# 1. List your fake users with a GET request
curl https://mockend.com/org/repo/users

# 2. Fake a creation with a POST
# (don't worry changes aren't persisted)
curl https://mockend.com/org/repo/users \
  -X POST \
  -H "Content-Type: application/json" \
  --data '{"name": "alice"}'

# 3. Access your GraphQL endpoint
https://mockend.com/org/repo/graphql
Test other random generators with this config:

github.com /org/repo/ .mockend.json
{
  "User": {
    "name": {
      "string": {}
    },
    "avatarUrl": {
      "regexp": "https://i\\.pravatar\\.cc/150\\?u=[0-9]{5}"
    },
    "statusMessage": {
      "string": [
        "working from home",
        "watching Netflix"
      ]
    },
    "email": {
      "regexp": "#[a-z]{5,10}@[a-z]{5}\\.[a-z]{2,3}"
    },
    "color": {
      "regexp": "#[0-9A-F]{6}"
    },
    "age": {
      "int": {
        "min": 21,
        "max": 100
      }
    },
    "isPublic": {
      "boolean": {}
    }
  }
}
See documentation for more details.
