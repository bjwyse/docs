Existing Amazon Cognito identity pools and user pools can be used with the Amplify Libraries by referencing them in your `amplifyconfiguration.json` file.

```json
{
    "auth": {
        "plugins": {
            "awsCognitoAuthPlugin": {
                "IdentityManager": {
                    "Default": {}
                },
                "CredentialsProvider": {
                    "CognitoIdentity": {
                        "Default": {
                            "PoolId": "[COGNITO IDENTITY POOL ID]",
                            "Region": "[REGION]"
                        }
                    }
                },
                "CognitoUserPool": {
                    "Default": {
                        "PoolId": "[COGNITO USER POOL ID]",
                        "AppClientId": "[COGNITO USER POOL APP CLIENT ID]",
                        "AppClientSecret": "[COGNITO USER POOL APP CLIENT SECRET]",
                        "Region": "[REGION]"
                    }
                },
                "Auth": {
                    "Default": {
                        "authenticationFlowType": "USER_SRP_AUTH"
                    }
                }
            }
        }
    }
}
```

- **CredentialsProvider**:
  - **Cognito Identity**:
    - **Default**:
      - **PoolID**: ID of the Amazon Cognito Identity Pool (e.g. `us-east-1:123e4567-e89b-12d3-a456-426614174000`)
      - **Region**: AWS Region where the resources are provisioned (e.g. `us-east-1`)
- **CognitoUserPool**:
  - **Default**:
    - **PoolId**: ID of the Amazon Cognito User Pool (e.g. `us-east-1_abcdefghi`)
    - **AppClientId**: ID for the client used to authenticate against the user pool
    - **AppClientSecret**: Secret for the client used to authenticate against the user pool
    - **Region**: AWS Region where the resources are provisioned (e.g. `us-east-1`)