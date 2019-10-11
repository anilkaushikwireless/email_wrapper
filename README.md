# email_wrapper
Sending and receiving outlook/exchange emails. 

There are various application which needs support for reading emails (like any chatbot or virtual personal assistants). 
Also such applications would need sending emails (Like any virtual personal assistant sending response on your behalf using your email account).

Sample client for sending email using exchange or outlook.
-------------------------------------------------------------------
        #if account type is Exchange or else account type id outlook.
        #Visit https://apps.dev.microsoft.com for registering your app for oauth athentication
        
        client_id = 'Value of client which you woukd get once you register at microsoft app dev center'
        client_secret = 'Value of secret which you woukd get once you register at microsoft app dev center'
        token_value = 'token value which you get after successfully authorizing the client for sending the email on your behalf'
        
        if acct_type == 'EXCHANGE':
            ms_client = Client(client_id, client_secret, 'v1.0', 'common', True)
        else:
            ms_client = Client(client_id, client_secret)

        ms_client.set_token(token_value)
        to_email_list = [to_email]
        ms_client.send_mail(subject, to_email_list, message)

