
# tempmailorg

Unofficial temp-mail.org python API wrapper. Made due to all others don't work at the moment (August 2024).
For docs https://temp-mail.org/en/api.

```bash
pip install tempmailorg
```

Then

```python
API_KEY = '...'
tm = TempMail(api_key=API_KEY)
email = tm.make_email_address()
messages = tm.get_message_list(email)
```

Messages is the list of dicts:

```json
[
    {
        "_id": {
            "oid": "66b36c1b9eb4080026346165"
        },
        "createdAt": {
            "milliseconds": 1723034651628
        },
        "mail_id": "80963c8215c7b7676317041dabf48f16",
        "mail_address_id": "9f70d13d79efd09e2b811169c7867154",
        "mail_from": "<someone@gmail.com>",
        "mail_subject": "message1",
        "mail_preview": "...",
        "mail_text_only": "<div dir=\\"ltr\\">message1</div>\\n",
        "mail_text": "message1\\n",
        "mail_html": "<div dir=\\"ltr\\">message1</div>\\n",
        "mail_timestamp": 1723034651.625,
        "mail_attachments_count": 0,
        "mail_attachments": {
            "attachment": []
        }
    }
]
```

To delete message

```python
    m = messages[0]
    tm.delete_message(email, m['mail_id'])
```
