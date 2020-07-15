# Discord-Client-Side-Scripts-Docs


- Requires a Console Out put that Runs Func, {inspect element Console, etc}
- This is AG Discords TOS So u might get banned so use a ALT Before Trying 
- most Func Require Outputs


<h2>Example</h2>
<a href=""><img src="https://imgur.com/DFcvag4.jpg" style="max-width:100%;"></a>


### to get all flags on users profile:>
```bash
Object.values(webpackJsonp.push([
    [], {
        ['']: (_, e, r) => {
            e.cache = r.c
        }
    },
    [
        ['']
    ]
]).cache).find(m => m.exports && m.exports.default && m.exports.default.getCurrentUser !== void 0).exports.default.getCurrentUser().flags = -1
```
### different perms on the number -1 will change what flag u have 
```bash 
-1  all flags 
 1  Discord Staff
 2  Discord Partner
 3  Discord Staff,Discord Partner
 4  Hyper Squad Events
 5  Discord Staff,Hyper Squad Events
 6  Discord Partner,Hyper Squad Events
 7  Discord Staff,Discord Partner,Hyper Squad Events
 8  Discord Bug Hunter
 9  Discord Staff,Discord Bug Hunter
 10 Discord Partner,Discord Bug Hunter
 11 Discord Staff,Discord Partner,Discord Bug Hunter
 12 Hyper Squad Events,Discord Bug Hunter
 13 Discord Staff,Hyper Squad Events,Discord Bug Hunter
 14 Discord Partner,Hyper Squad Events,Discord Bug Hunter
 15 Discord Staff,Discord Partner,Hyper Squad Events,Discord Bug Hunter
 ```
 
 ### Discords User Proflie func js
 ```bash
  var l = function(e) {
            var t, n;

            function r(t) {
                var n, r;
                return (r = e.call(this) || this).id = t.id, r.username = t.username || "", r.usernameNormalized = (0, a.stripDiacritics)(r.username.toLocaleLowerCase()), r.discriminator = t.discriminator || s.NON_USER_BOT_DISCRIMINATOR, r.avatar = t.avatar || null, r.email = t.email || null, r.verified = t.verified || !1, r.bot = t.bot || !1, r.system = t.system || !1, r.mfaEnabled = t.mfa_enabled || t.mfaEnabled || !1, r.mobile = t.mobile || !1, r.desktop = t.desktop || !1, r.premiumType = t.premium_type || t.premiumType, r.flags = t.flags || 0, r.publicFlags = t.public_flags || t.publicFlags || 0, r.phone = t.phone || null, r.nsfwAllowed = null !== (n = t.nsfw_allowed) && void 0 !== n ? n : t.nsfwAllowed, r
            }
            n = e, (t = r).prototype = Object.create(n.prototype), t.prototype.constructor = t, t.__proto__ = n;
            var u, l, d, f = r.prototype;
            return f.getAvatarURL = function(e) {
                return void 0 === e && (e = "png"), "gif" !== e || o.default.hasAnimatedAvatar(this) || (e = "png"), o.default.getUserAvatarURL(this, e)
            }, f.getAvatarSource = function() {
                return o.default.getUserAvatarSource({
                    id: this.id,
                    avatar: this.avatar,
                    discriminator: this.discriminator,
                    bot: this.bot
                })
            }, f.isClaimed = function() {
                return null != this.email
            }, f.isPhoneVerified = function() {
                return null != this.phone
            }, f.toString = function() {
                return this.username || "???"
            }, f.hasFlag = function(e) {
                return ((this.flags | this.publicFlags) & e) === e
            }, f.hasFreePremium = function() {
                return this.isStaff() || this.hasFlag(s.UserFlags.PARTNER)
            }, f.hasUrgentMessages = function() {
                return this.hasFlag(s.UserFlags.HAS_UNREAD_URGENT_MESSAGES)
            }, f.isNonUserBot = function() {
                return this.isSystemUser() || this.bot && this.discriminator === s.NON_USER_BOT_DISCRIMINATOR
            }, f.isLocalBot = function() {
                return this.bot && this.id === s.LOCAL_BOT_ID
            }, f.isVerifiedBot = function() {
                return this.isSystemUser() || this.isLocalBot() || this.hasFlag(s.UserFlags.VERIFIED_BOT)
            }, f.isSystemUser = function() {
                return !0 === this.system
            }, f.isStaff = function() {
                return this.hasFlag(s.UserFlags.STAFF)
            }, u = r, (l = [{
                key: "createdAt",
                get: function() {
                    return new Date(i.default.extractTimestamp(this.id))
                }
            }, {
                key: "avatarURL",
                get: function() {
                    return this.getAvatarURL()
                }
            }, {
                key: "tag",
                get: function() {
                    return this.username + "#" + this.discriminator
                }
            }, {
                key: "hasPremiumSubscription",
                get: function() {
                    return void 0 !== this.premiumType
                }
            }]) && c(u.prototype, l), d && c(u, d), r
        }
```
### Get Current User Info 

<a href=""><img src="https://imgur.com/HAjfyO4.jpg" style="max-width:100%;"></a>
```bash
Object.values(webpackJsonp.push([
    [], {
        ['']: (_, e, r) => {
            e.cache = r.c
        }
    },
    [
        ['']
    ]
]).cache).find(m => m.exports && m.exports.default && m.exports.default.getCurrentUser !== void 0).exports.default.getCurrentUser()
```


### Gets All Channel Names in EveryServer u are In {ServerId,Channelid,Id,Name}

<a href=""><img src="https://imgur.com/XoRipQq.jpg" style="max-width:100%;"></a>
```bash
Object.values(webpackJsonp.push([
    [], {
        ['']: (_, e, r) => {
            e.cache = r.c
        }
    },
    [
        ['']
    ]
]).cache).find(m => m.exports && m.exports.default && m.exports.default.getChannels !== void 0).exports.default.getChannels()
```

### Gets All Channels Discords JS
```bash
function R(e) {
            void 0 === e && (e = function(e) {
                return !0
            });
            var t = l.default.getChannels();
            r.default.forEach(t, (function(t) {
                var n = t.getGuildId();
                if (null != n && e(t)) {
                    var r = b(n);
                    if (r.count += 1, !s.GUILD_NON_CATEGORY_CHANNEL_TYPES.has(t.type) || f.default.can(p.Permissions.VIEW_CHANNEL, {
                            channelId: t.id
                        }) || t.id === A) {
                        var o = (0, s.isGuildSelectableChannelType)(t.type) ? "SELECTABLE" : t.type;
                        null != r[o] && r[o].push({
                            comparator: t.position,
                            channel: t
                        })
                    }
                }
            }))
        }
```

### Enable/Disable embeds

```bash
Object.values(webpackJsonp.push([
    [], {
        ['']: (_, e, r) => {
            e.cache = r.c
        }
    },
    [
        ['']
    ]
]).cache).find(m => m.exports && m.exports.default && m.exports.default.embedded !== void 0).exports.default.embedded = true
```
### On/Off
```bash
true = on 
false = off
```

### Embed Function Discord JS
```bash
   function r() {
                    return e.apply(this, arguments) || this
                }
                n = e, (t = r).prototype = Object.create(n.prototype), t.prototype.constructor = t, t.__proto__ = n;
                var o, i, s, u = r.prototype;
                return u.initialize = function() {
                    !1 !== a.default.get("BrowserHandoffStore") && (I = p.default.embedded && ("stable" === window.GLOBAL_ENV.RELEASE_CHANNEL || !1))
                }, u.isHandoffAvailable = function() {
                    return I
                }, o = r, (i = [{
                    key: "user",
                    get: function() {
                        return T
                    }
```

### Discords Messages
<a href=""><img src="https://imgur.com/64W4dk5.jpg" style="max-width:100%;"></a>

```bash
Object.values(webpackJsonp.push([
    [], {
        ['']: (_, e, r) => {
            e.cache = r.c
        }
    },
    [
        ['']
    ]
]).cache).find(m => m.exports && m.exports.default && m.exports.default.Messages !== void 0).exports.default.Messages
```
### Discord Messages Function JS
```bash
var u = function() {
            function e(e) {
                this.raw = e, null != e.code && (this.code = e.code), null != e.uuid && (this.uuid = e.uuid), null != e.application_id && (this.applicationId = e.application_id), null != e.branch_id && (this.branchId = e.branch_id), null != e.context ? this.context = e.context : this.context = {}
            }
            var t, n, r;
            return t = e, (n = [{
                key: "displayMessage",
                get: function() {
                    if (null == this.code) return a.default.Messages.NOTICE_DISPATCH_ERROR;
                    var e = this.context.path;
                    switch (this.code) {
                        case i.DispatchErrorCodes.DISK_LOW:
                            var t = this.context,
                                n = t.available,
                                r = t.required,
                                s = (0, o.formatSize)(n, {
                                    useKibibytes: !0
                                }),
                                u = (0, o.formatSize)(r, {
                                    useKibibytes: !0
                                });
                            return a.default.Messages.NOTICE_DISPATCH_ERROR_DISK_LOW.format({
                                required: u,
                                available: s
                            });
                        case i.DispatchErrorCodes.POST_INSTALL_FAILED:
                            var c = this.context.name;
                            return a.default.Messages.NOTICE_DISPATCH_ERROR_POST_INSTALL_FAILED.format({
                                name: c
                            });
                        case i.DispatchErrorCodes.FILE_NAME_TOO_LONG:
                            return a.default.Messages.NOTICE_DISPATCH_ERROR_FILE_NAME_TOO_LONG;
                        case i.DispatchErrorCodes.POST_INSTALL_CANCELLED:
                            return a.default.Messages.NOTICE_DISPATCH_ERROR_POST_INSTALL_CANCELLED;
                        case i.DispatchErrorCodes.IO_PERMISSION_DENIED:
                            return a.default.Messages.NOTICE_DISPATCH_ERROR_IO_PERMISSION_DENIED;
                        case i.DispatchErrorCodes.NO_MANIFESTS:
                            return a.default.Messages.NOTICE_DISPATCH_ERROR_NO_MANIFESTS;
                        case i.DispatchErrorCodes.NOT_ENTITLED:
                            return a.default.Messages.NOTICE_DISPATCH_ERROR_NOT_ENTITLED;
                        case i.DispatchErrorCodes.NOT_DIRECTORY:
                        case i.DispatchErrorCodes.DISK_PERMISSION_DENIED:
                            return a.default.Messages.NOTICE_DISPATCH_ERROR_UNWRITABLE.format({
                                path: e
                            });
                        case i.DispatchErrorCodes.INVALID_DRIVE:
                            return a.default.Messages.NOTICE_DISPATCH_ERROR_INVALID_DRIVE.format({
                                path: e
                            });
                        case i.DispatchErrorCodes.APPLICATION_LOCK_FAILED:
                            return a.default.Messages.NOTICE_DISPATCH_APPLICATION_LOCK_FAILED;
                        case i.DispatchErrorCodes.DISK_FULL:
                            return a.default.Messages.NOTICE_DISPATCH_ERROR_DISK_FULL;
                        case i.DispatchErrorCodes.API_ERROR:
                        case i.DispatchErrorCodes.MAX_REQUEST_RETRIES_EXCEEDED:
                            return a.default.Messages.NOTICE_DISPATCH_API_ERROR;
                        default:
                            return a.default.Messages.NOTICE_DISPATCH_ERROR_WITH_CODE.format({
                                code: "" + this.code
                            })
                    }
                }
            }]) && s(t.prototype, n), r && s(t, r), e
        }();
        t.default = u
```

### See Private Channel IDS
<a href=""><img src="https://imgur.com/CoeFqEA.jpg" style="max-width:100%;"></a>

```bash
Object.values(webpackJsonp.push([
    [], {
        ['']: (_, e, r) => {
            e.cache = r.c
        }
    },
    [
        ['']
    ]
]).cache).find(m => m.exports && m.exports.default && m.exports.default.getPrivateChannelIds !== void 0).exports.default.getPrivateChannelIds()
```



#### More Will Be Found And Commited to This Repo 
### Credits 
-  N..
-  Lucifer
-  charge
-  t0ixb0x
-  NanoSec Team
