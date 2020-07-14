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

