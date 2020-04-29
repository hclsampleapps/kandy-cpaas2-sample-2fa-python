# kandy-cpaas2-sample-2fa-python

![Maintenance](https://img.shields.io/maintenance/no/2020?style=flat-square)

This is an elementary  login authentication use case of two-factor authentication via SMS. The main focus of this application is to understand and implement the 2FA flow, so least amount of stress is given to the authentication/login mechanism.

## Installation/Setup
1. Install the [Python 3.7.0](https://www.python.org/downloads/release/python-370/) on your system (mandatory to have). 
2. After installation, to check if `pip` is installed or not, run 
```bash
pip -V 
```
3. Update the `constants.py` file with the apropriate credentials. Please refer the configuration section for more details.
4. To install dependencies, run
```bash
pip install cpaassdk
pip install pipenv
pipenv install
```
5. To start the server, run
```bash
python twofactor.py
```

## Configuration
There are a few configurations (check `constants.py` file) to make the application simpler and help us focus on the key aspects a two-factor authentication system via SMS. Some of the variables are pre-filled and some are left blank which are left on the user to place appropriate values. All the variables are mandatory.

ENV KEY            | Description
-------            | -----------
CLIENT_ID          | Private project key
CLIENT_SECRET      | Private project secret
BASE_URL           | URL of the CPaaS server to use
SENDER_NUMBER      | Phone number purchased in CPaaS portal (sender phone number)
DESTINATION_NUMBER | Phone number that would receive the verification code
TEST_EMAIL         | Email used in the login screen of the application
TEST_PASSWORD      | Password to be entered against the EMAIL provided

## Usage
The application comprises of three simple pages, login, code verification, dashboard/portal

- On opening the application in the browser, the login screen is presented. The user needs to enter the `Email` / `Password` that are specified in the `costants.py` file and click on the `Login` button.
- Once the credentials are verified, a verification code is sent out to the phone number and redirected to the code verification page. This phone number corresponds to the one entered in the `constants.py` file as `SENDER_NUMBER`.
- The user now needs to enter the verification code received in the mentioned phone number and click `Verify` button.
- The application verifies the entered code. If the code validates, the user is redirected to the dashboard section; else the user will be promoted with an error alert `Code invalid or expired` and is required to re-enter the verification code.
- As the user is authenticated, the dashboard opens up. The user can logout from the dashboard and login screen would be presented.

