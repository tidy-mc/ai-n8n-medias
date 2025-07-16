# ai-n8n-medias

TwiML code for STT

<?xml version="1.0" encoding="UTF-8"?>
<Response>
  <!-- 1. Play greeting -->
  <Play>
    https://raw.githubusercontent.com/tidy-mc/ai-n8n-medias/main/20250715onboarding_1.mp3
  </Play>

  <!-- 2. Speech recognition only -->
  <Gather
    input="speech"
    action="https://intelagent-last.app.n8n.cloud/webhook-test/webhook/twilio-gather"
    speechTimeout="3"
    timeout="15"
    language="en-US"
    hints="support,sales,help,account"
  >
    <Say>Please speak your message now.</Say>
  </Gather>

  <!-- 3. Fallback -->
  <Say>We didn't hear your response. Goodbye!</Say>
  <Hangup/>
</Response>
