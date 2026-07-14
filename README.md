# lists

Community-managed lists consumed by Bitsocial clients (5chan, Seedit).

Submit a pull request to have your community added, or contact devs on Telegram [@bitsocialnet](https://t.me/bitsocialnet).

In the future, this process will be automated by voting.

## Repository Layout

- `5chan-directories/5chan-<code>-directory.json`: candidate boards for each 5chan directory code. 5chan builds the active directory list by reading these files and choosing the highest-ranked board in each file.
- `5chan-directories/5chan-directories-defaults.json`: expected 5chan UX defaults and rules keyed by directory code, including directory title and feature defaults. These defaults apply to the directory, not to individual candidate boards.
- `5chan-directories/bitsocial-seeder-communities.json`: seeder-only compatibility list for public communities that existing `bitsocial-seeder` releases should seed even though they are not 5chan directories. It can temporarily mirror communities from another official directory while old seeders only poll `5chan-directories`; remove mirrored entries once those installations have migrated to releases that consume all official directory lists. The filename intentionally does not match `5chan-<code>-directory.json`, so 5chan directory consumers ignore it.
- `seedit-directories/seedit-<code>-directory.json`: retired Seedit directory data retained for seeder compatibility. Current Seedit clients use `seedit-default-subscriptions.json`; do not treat these directory files as Seedit navigation or subscription targets.
- `seedit-default-subscriptions.json`: the versioned list of Seedit's default communities. New accounts subscribe to these communities by default; existing users review later revisions before changing their subscriptions.
- `whitelist-challenge.json`: public keys exempted from posting challenges.

>### What is this?
These lists provide default discovery for Bitsocial clients. New Seedit accounts subscribe to its default communities, while existing users review later revisions before changing their subscriptions. Any user can still connect directly to communities outside these lists.

## Requirements to have your community included
- 99% uptime: your community must be online 24/7 to appear by default in our clients.
- non-random topic: communitys about specific topics are preferred, such as technology, movies, anime, business, etc.
- unique topic: please check if your community's topic is already taken in our list.
- no self-promotion, unless in partnership: please contact the @bitsocialnet org devs for partnership inquiries.

>### Isn't this list supposed to be decentralized? Why are there requirements to have my community included?
This list is not mandatory on Bitsocial itself, which is fully decentralized: nobody can stop a Bitsocial user from connecting P2P to your community, if they know its address.

However, the developer of each Bitsocial client effectively holds veto power over the list, since the list has to be manually implemented in the frontend code of the interface/client. If you don't like how a Bitsocial client dev implements this list, you are always free to create your own Bitsocial client, even using your own list.

Our web and desktop clients (Seedit, 5chan) don't use blacklists. You can use our clients to connect to any specific community by using its address, whether it's included in this default list or not.

## License

GPL-3.0-or-later — see [LICENSE](LICENSE).
