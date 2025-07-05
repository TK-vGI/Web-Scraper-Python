import requests
import json

ERR_MSG = "\nInvalid resource!"

def main():

    print("Input the URL:")
    user_url = input().strip()

    headers = {"Accept": "application/json"}  # Ensure we get JSON response

    try:
        response = requests.get(user_url, headers=headers, timeout=10)

        if response.status_code == 200:
            try:
                # data = response.json()
                data = json.loads(response.content)
                if data['status'] == 200 and ('joke' in data.keys()):
                    print(data['joke'])
                else:
                    print(ERR_MSG)  # Empty JSON

            except ValueError:
                print(ERR_MSG)  # Not a JSON response
        else:
            print(ERR_MSG)  # Non-200 status code

    except requests.RequestException:
        print(ERR_MSG)  # Network or request error


if __name__ == '__main__':
    main()