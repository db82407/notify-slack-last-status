# notify-slack-last-status
The Slack GitHub app cannot subscribe **only** to failed workflows.

This action notifies Slack whenever a workflow fails and also the first time it succeeds after a failure.

It uses [Mercymeilya/last-workflow-status](https://github.com/MercymeIlya/last-workflow-status) and [ravsamhq/notify-slack-action](https://github.com/ravsamhq/notify-slack-action)

## Usage

Add this as the last step in any job for which you want notification of failure:

```yaml
      - name: Notify Slack
        if: always()
        uses: db82407/notify-slack-last-status@main
        with:
          github_token: ${{ secrets.GITHUB_TOKEN }}
          slack_webhook_url: ${{ secrets.SLACK_WEBHOOK_URL }}
```

