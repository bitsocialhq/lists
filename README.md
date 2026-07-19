# lists

Community-managed lists consumed by Bitsocial clients (5chan, Seedit).

Submit a pull request to have your community added, or contact devs on Telegram [@bitsocialnet](https://t.me/bitsocialnet).

In the future, this process will be automated by voting.

## Repository Layout

- `5chan-directories/5chan-<code>-directory.json`: candidate boards for each 5chan directory code. 5chan builds the active directory list by reading these files and choosing the highest-ranked board in each file.
- `5chan-directories/5chan-directories-defaults.json`: expected 5chan UX defaults and rules keyed by directory code, including directory title and feature defaults. These defaults apply to the directory, not to individual candidate boards.
- `5chan-directories/bitsocial-seeder-communities.json`: seeder-only compatibility list for public communities that existing `bitsocial-seeder` releases should seed even though they are not 5chan directories. It can temporarily mirror communities from another official directory while old seeders only poll `5chan-directories`; remove mirrored entries once those installations have migrated to releases that consume all official directory lists. The filename intentionally does not match `5chan-<code>-directory.json`, so 5chan directory consumers ignore it.
- `seedit-directories/seedit-<code>-directory.json`: versioned candidates for each contested Seedit short route. `/s/<code>` recommends the highest-rated finalized candidate, but subscriptions and post permalinks always use exact community addresses.
- `seedit-directories/seedit-directories-defaults.json`: display metadata for Seedit's short routes, keyed by directory code.
- `seedit-default-subscriptions.json`: the versioned list of exact communities Seedit subscribes new accounts to by default. `directoryCode` and `directoryRevision` record which finalized short-route snapshot selected an entry, when applicable; existing users review later winner or membership changes before their exact subscriptions change.
- `whitelist-challenge.json`: public keys exempted from posting challenges.

>### What is this?
These lists provide default discovery for Bitsocial clients. Seedit's short routes are mutable recommendations, while account subscriptions and permanent post links remain pinned to exact addresses. New Seedit accounts subscribe to exact default communities, and existing users review later changes unless they explicitly enabled automatic switching for a route. Any user can still connect directly to communities outside these lists.

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
