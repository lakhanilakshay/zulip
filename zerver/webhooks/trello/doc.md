Get Zulip notifications from your Trello boards!

!!! tip ""
    Note that [Zapier][1] is usually a simpler way to
    integrate Trello with Zulip.

[1]: ./zapier

1. {!create-stream.md!}

1. {!create-bot-construct-url-indented.md!}

1. **Log in to Trello**, and collect the following three items:

    * **Board ID**: Go to your Trello board. The URL should look like
      `https://trello.com/b/<BOARD_ID>/<BOARD_NAME>`. Note down the
      `<BOARD_ID>`.

    * **API Key**: Go to <https://trello.com/1/appkey/generate>. Note down the
      key listed under **Developer API Keys**.

    * **User Token**: Go to <https://trello.com/1/appkey/generate>. Under
      **Developer API Keys**, click on the **Token** link. Click on **Allow**.
      Note down the token generated.

1.  [Trello's webhook API][webhooks] does not have a web configuration
    UI, so outgoing notifications from Trello have to be configured
    using the Trello API.  We provide a convenient Python script that
    you can use to configure Trello's webhook API for Zulip.

    Make sure you have a working copy of Python. If you're running
    macOS or Linux, you very likely already do. If you're running
    Windows you may or may not.  If you don't have Python, follow the
    installation instructions
    [here](https://realpython.com/installing-python/). Note that you
    do not need the latest version of Python; anything 2.7 or higher
    will do.

1. Download [zulip-trello.py][2]. `Ctrl+s` or `Cmd+s` on that page should
   work in most browsers.

1. Run the `zulip-trello` script in a terminal, after replacing the
   arguments with the values collected above.

    ```
    python zulip_trello.py --trello-board-name <trello_board_name> \
                           --trello-board-id   <trello_board_id> \
                           --trello-api-key  <trello_api_key> \
                           --trello-token <trello_token> \
                           --zulip-webhook-url <zulip_webhook_url>
    ```

    The `zulip_trello.py` script only needs to be run once, and can be run
    on any computer with python.

1. You can delete `zulip_trello.py` from your computer if you'd like.

[2]: https://raw.githubusercontent.com/zulip/python-zulip-api/master/zulip/integrations/trello/zulip_trello.py
[webhooks]: https://developers.trello.com/page/webhooks

{!congrats.md!}

![](/static/images/integrations/trello/001.png)
