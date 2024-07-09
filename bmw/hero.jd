const {
  zokou
} = require("../framework/zokou");
const s = require("../set");
const fs = require('fs');
function getDescriptionFromEnv(_0x540f38) {
  filePath = "./app.json";
  const _0x2fb026 = fs.readFileSync(filePath, "utf-8");
  const _0x94eef1 = JSON.parse(_0x2fb026);
  const _0x7ed924 = _0x94eef1.env[_0x540f38];
  return _0x7ed924 && _0x7ed924.description ? _0x7ed924.description : "The environment variable description was not found.";
}
zokou({
  'nomCom': "getallvar",
  'categorie': 'HEROKU'
}, async (_0x4175bd, _0x165dc2, _0x4c72c7) => {
  const {
    ms: _0x17eca2,
    repondre: _0x52092f,
    superUser: _0x4dc369,
    auteurMessage: _0x29341a
  } = _0x4c72c7;
  if (!_0x4dc369) {
    _0x52092f("This command is for my owner only!");
    return;
  }
  ;
  let _0x1033ce = [{
    'nom': "AUTO_VIEW_STATUS",
    'choix': ['yes', "no"]
  }, {
    'nom': "AUTO_SAVE_STATUS",
    'choix': ['yes', "no"]
  }, {
    'nom': "PM_PERMIT",
    'choix': ['yes', "no"]
  }, {
    'nom': "BOT_MODE",
    'choix': ["yes', "no"]
  }, {
    'nom': 'STARTING_MESSAGE',
    'choix': ['yes', "no"]
  }, {
    'nom': "AUTO_READ_MESSAGES",
    'choix': ['yes', "no"]
  }, {
    'nom': 'PRESENCE',
    'choix': ["1", "2", "3", "nothing"]
  }];
  let _0x514865 = "    ╭──────༺♡༻──────╮\n              BMW VARS\n    ╰──────༺♡༻──────╯\n\n";
  for (v = 0x0; v < _0x1033ce.length; v++) {
    _0x514865 += v + 0x1 + "- *" + _0x1033ce[v].nom + "*\n";
  }
  _0x514865 += "\n*Please Choose a variable by its number*";
  let _0x3ea0b1 = await _0x165dc2.sendMessage(_0x4175bd, {
    'text': _0x514865
  }, {
    'quoted': _0x17eca2
  });
  console.log(_0x3ea0b1);
  let _0x4868dd = await _0x165dc2.awaitForMessage({
    'chatJid': _0x4175bd,
    'sender': _0x29341a,
    'timeout': 0xea60,
    'filter': _0x3f3bff => _0x3f3bff.message.extendedTextMessage && _0x3f3bff.message.extendedTextMessage.contextInfo.stanzaId == _0x3ea0b1.key.id && _0x3f3bff.message.extendedTextMessage.text > 0x0 && _0x3f3bff.message.extendedTextMessage.text <= _0x1033ce.length
  });
  let _0x52a975 = _0x4868dd.message.extendedTextMessage.text - 0x1;
  let {
    nom: _0x110314,
    choix: _0x4c58c5
  } = _0x1033ce[_0x52a975];
  let _0x48d759 = "    ╭──────༺♡༻──────╮\n              BMW VARS\n    ╰──────༺♡༻──────╯\n\n";
  _0x48d759 += "*Variable Name* :" + _0x110314 + "\n";
  _0x48d759 += "*Description* :" + getDescriptionFromEnv(_0x110314) + "\n\n";
  _0x48d759 += "┌────── ⋆⋅☆⋅⋆ ──────┐\n\n";
  for (i = 0x0; i < _0x4c58c5.length; i++) {
    _0x48d759 += "* *" + (i + 0x1) + "* => " + _0x4c58c5[i] + "\n";
  }
  _0x48d759 += "\n└────── ⋆⋅☆⋅⋆ ──────┘\n\n*Now reply this message with the number that matches your choice.*";
  let _0x1a52dc = await _0x165dc2.sendMessage(_0x4175bd, {
    'text': _0x48d759
  }, {
    'quoted': _0x4868dd
  });
  let _0x3b4b70 = await _0x165dc2.awaitForMessage({
    'chatJid': _0x4175bd,
    'sender': _0x29341a,
    'timeout': 0xea60,
    'filter': _0x319df8 => _0x319df8.message.extendedTextMessage && _0x319df8.message.extendedTextMessage.contextInfo.stanzaId == _0x1a52dc.key.id && _0x319df8.message.extendedTextMessage.text > 0x0 && _0x319df8.message.extendedTextMessage.text <= _0x4c58c5.length
  });
  let _0x6212c3 = _0x3b4b70.message.extendedTextMessage.text - 0x1;
  const _0x131b4f = require('heroku-client');
  const _0x7f76e6 = new _0x131b4f({
    'token': s.HEROKU_APY_KEY
  });
  let _0x22dce0 = "/apps/" + s.HEROKU_APP_NAME;
  await _0x7f76e6.patch(_0x22dce0 + "/config-vars", {
    'body': {
      [_0x110314]: _0x4c58c5[_0x6212c3]
    }
  });
  await _0x52092f("That Heroku variable is changing, The bot is restarting....");
});
function changevars(_0x423587, _0x4b1735) {
  king({
    'nomCom': _0x423587,
    'categorie': "HEROKU"
  }, async (_0x48d756, _0x44cccc, _0x134f15) => {
    const {
      arg: _0xcefbf5,
      superUser: _0x22266a,
      repondre: _0x516958
    } = _0x134f15;
    if (!_0x22266a) {
      _0x516958("This command is for my owner only!");
      return;
    }
    ;
    if (s.HEROKU_APP_NAME == null || s.HEROKU_APY_KEY == null) {
      _0x516958("Fill in the HEROKU_APP_NAME and HEROKU_API_KEY environment variables");
      return;
    }
    ;
    if (!_0xcefbf5[0x0]) {
      _0x516958(getDescriptionFromEnv(_0x4b1735));
      return;
    }
    ;
    const _0x926c31 = require("heroku-client");
    const _0x7ecbeb = new _0x926c31({
      'token': s.HEROKU_APY_KEY
    });
    let _0xdad8c7 = '/apps/' + s.HEROKU_APP_NAME;
    await _0x7ecbeb.patch(_0xdad8c7 + '/config-vars', {
      'body': {
        [_0x4b1735]: _0xcefbf5.join(" ")
      }
    });
    await _0x516958("That Heroku variable is changing, The bot is restarting....");
  });
}
;
changevars("setprefix", "PREFIX");
changevars("menulinks", "BOT_MENU_LINKS");
